# MH-Clinic: Engineering & Developer Architecture Deck

> **Audience:** Software Engineers, Database Architects, Security Auditors, and DevOps/QA Engineers  
> **Stack:** Next.js App Router (TypeScript + Zod) · PostgreSQL 15/16 (`SECURITY DEFINER` + RLS) · Node.js Workers · Biome · Playwright

---

## Slide 1: Core Architectural Tenets
1. **Database as the Security Boundary:**
   - The web tier connects as the unprivileged `clinic_app` role.
   - All table access is denied by default (`REVOKE ALL FROM PUBLIC, clinic_app, clinic_auth`); reads and writes occur exclusively through `SECURITY DEFINER` functions with `SET search_path = pg_catalog, clinic`.
2. **Verified Actor Context:**
   - Every protected API route uses `withProgramActor(request, fn, { pinActor: true })` and every SSR page uses `withVerifiedActorTransaction(getDatabasePool(), claim, fn)`.
   - PostgreSQL verifies an HMAC-signed actor claim (`clinic.set_actor_context`) and checks active session + mandatory MFA (`clinic.require_actor`).
3. **Immutable History & CAS:**
   - Clinical notes, prescriptions, demographics, and financial events are append-only (`BEFORE UPDATE OR DELETE` immutability triggers).
   - Admin and clinical mutations use `expectedRevision` Compare-And-Swap (`409 Conflict` on stale writes) and `commandId` UUID idempotency.

---

## Slide 2: End-to-End Request Lifecycle

```mermaid
sequenceDiagram
  participant Client as Browser / Client
  participant Next as Next.js Route / SSR
  participant Guard as withProgramActor / RLS
  participant DB as PostgreSQL (clinic_app)

  Client->>Next: Request + Session Cookie
  Next->>Guard: Verify Session, MFA & HMAC Actor Claim
  Guard->>DB: SET SESSION AUTHORIZATION clinic_app + set_actor_context()
  DB->>DB: clinic.require_actor() + scope check + record_staff_read_access()
  DB-->>Next: Typed JSONB payload (k >= 5 enforced for aggregates)
  Next->>Next: Zod schema validation (.parse)
  Next-->>Client: 200 JSON / SSR HTML (Cache-Control: no-store)
```

---

## Slide 3: Key Codebase Directories (`mh-clinic`)
- `apps/web/src/modules/` — Domain models, Zod contracts, and pure business logic (`reports/`, `assessments/`, `formulary-publication/`, `helpline/`, `coordinator-agent/`, `ihc/`, `session-notes/`).
- `apps/web/src/app/api/` — Next.js Route Handlers (`admin/`, `staff/`, `professional/`, `client/`, `public/`).
- `apps/web/src/app/` — App Router SSR pages & client workspaces.
- `apps/web/scripts/check-read-audit-coverage.cjs` — Static gate ensuring **every** protected GET/POST route and SSR page declares an audited read mechanism.
- `db/migrations/` — Sequential, append-only SQL migrations (`0001` through `0689`).
- `services/` — Standalone Node.js workers (`accounting`, `crm`, `notification-sender`, `helpline-issuer`, `helpline-redemption`, etc.).

---

## Slide 4: Privacy, $k$-Anonymity & Migration Portability Rules
- **No Hardcoded Tenants:** `tools/check_migration_portability.py` rejects literal tenant slugs (e.g., `'adb'`, `'aventus'`) in prospective migrations; behavior is driven by `clinic.policy_values`.
- **Database-Enforced $k$-Anonymity:** Aggregate reports (`R01`–`R30`, Sponsor Portal) compute `floor := greatest(5, clinic.sponsor_minimum_cohort_size(...))` in SQL and return `status: 'suppressed'` with `NULL` counts whenever `distinct_clients < floor`.
- **Read-Audit Bounds:** `clinic.record_staff_read_access` enforces `p_range_start/end IS NULL` for `'admin_configuration'` and `p_range_end - p_range_start <= 89` for `'operational_report'`.

---

## Slide 5: Verification & CI Gates
1. **Static & Lint:** `npm run check --prefix apps/web` (Biome + `check-read-audit-coverage.cjs` + `check-public-edge-upstreams.cjs`) & `npm run typecheck --prefix apps/web`.
2. **Unit & Build:** `npm test` & `npm run build --prefix apps/web`.
3. **Database & Inventory:** `python3 tools/check_migration_portability.py` & `python3 tools/audit_persona_coverage.py --check`.
4. **Full Containerized Wave Gate:** `sh scripts/verify-master-wave.sh` (disposable PostgreSQL 16 + Accounting + CRM + Playwright multi-profile browser suite).
