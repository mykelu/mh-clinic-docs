# Training 03: Company & Branch Administrator Curriculum

> **Navigation:** [Knowledge Base Home](../README.md) · [Master Index](../INDEX.md) · [Admin Persona Guide](../personas/01-company-and-branch-administrator.md) · [Role Exercises & Labs](01-role-exercises-and-labs.md) · [Go-Live Checklist](02-content-and-data-onboarding-checklist.md)

> [!IMPORTANT]
> **Training Environment Rule:** Perform all exercises in a staging or training tenant using **synthetic data only** (e.g., `admin.demo@example.test`, `clinician.demo@example.test`, `PRC 0000001`). Never enter real clinician license numbers, real patient PHI, or live HMO credentials.

---

## Curriculum Overview

| Module | Topic | Target Routes | Est. Time |
| :--- | :--- | :--- | :--- |
| **Module 1** | Identity, Mandatory MFA, RBAC & Staff Provisioning | `/admin/user-access`, `/admin/staff-invitations`, `/admin/professional-credential-validity` | 25 min |
| **Module 2** | Organization Structure, Branches, Rooms & 8-Gate Policies | `/admin/organization-structure`, `/admin/locations`, `/admin/rooms`, `/admin/booking-policies` | 30 min |
| **Module 3** | Service Catalog, HMO Contracts, Accounting & Refunds | `/admin/services`, `/admin/hmo-contracts`, `/admin/hmo-payer-review`, `/admin/cancellation-refunds` | 30 min |
| **Module 4** | Clinical Governance, Supervision & Assessment Controls | `/admin/supervision`, `/admin/clinical-note-approvers`, `/admin/encounter-policies`, `/admin/assessments` | 25 min |
| **Module 5** | RA 10173 Privacy, Audit Logs, Exports & Report Studio | `/admin/audit`, `/admin/compliance-exports`, `/admin/reports-studio`, `/staff/reports` | 25 min |
| **Module 6** | Brand Portals, IHC Setup, Learning Hub & Helpline | `/admin/brands`, `/admin/ihc-workplan`, `/admin/learning-hub`, `/admin/risk-response` | 20 min |
| **Capstone** | End-to-End Branch Launch Simulation | All `/admin/*` | 25 min |

---

## Module 1: Identity, Mandatory MFA, RBAC & Staff Provisioning

### Learning Objectives
- Enroll and verify mandatory MFA (`WP-01`) for administrative accounts.
- Provision staff with **least-privilege RBAC** (`FRONT_DESK`, `PSYCHIATRIST`, `PSYCHOLOGIST`, `PSYCHOMETRICIAN`, `COUNSELOR`, `CASE_MANAGER`, `BILLING`, `BRANCH_ADMIN`).
- Enforce **PRC / PTR / S2** credential validity gates for clinicians.

### Hands-On Steps
1. **MFA & Idle Lock:** Sign in as `admin.demo@example.test`, complete TOTP or Passkey enrollment at `/mfa`, and verify the 15-minute idle lock policy.
2. **Invite Staff (`/admin/staff-invitations`):**
   - Invite `md.demo@example.test` with role `PSYCHIATRIST` and assign a single branch.
   - Invite `rpm.demo@example.test` with role `PSYCHOMETRICIAN` and `rpsy.demo@example.test` with role `PSYCHOLOGIST`.
3. **Credential Validity (`/admin/professional-credential-validity`):**
   - Enter synthetic `PRC`, `PTR`, and `S2` numbers with future expiration dates for `md.demo@example.test`.
   - Test an **expired PRC date** on a dummy clinician and confirm the system blocks eRx/encounter signing.
4. **Access Audit (`/admin/user-access`):**
   - Confirm no user holds unnecessary `COMPANY_ADMIN` or `break_glass` privileges.

---

## Module 2: Organization Structure, Branches, Rooms & 8-Gate Policies

### Learning Objectives
- Configure multi-branch hierarchy, physical/telehealth rooms, and equipment.
- Configure the **6-Layer Policy Engine** and verify slot generation with the **8-Gate Simulator**.

### Hands-On Steps
1. **Branch Setup (`/admin/locations`):** Create a synthetic branch (`Training Annex — Makati`) with timezone `Asia/Manila` and operating hours `08:00–18:00`.
2. **Rooms & Equipment (`/admin/rooms`, `/admin/equipment`):** Add `Consult Room 1` (In-Person) and `Telehealth Pod A` (Virtual).
3. **Professional Schedules (`/admin/professional-schedules`):** Assign `md.demo@example.test` to `Consult Room 1` (Mon–Wed) and `Telehealth Pod A` (Thu–Fri).
4. **Booking Policies (`/admin/booking-policies`, `/admin/service-channel-policies`):**
   - Set buffer/turnover minutes, cancellation windows, and allowed modalities (`IN_PERSON` / `TELEHEALTH`).
5. **8-Gate Verification:** Open `/schedule` and verify slots only appear where all 8 gates (hours, shift, room, credential match, buffer, double-book guard, HMO branch eligibility, age/consent) pass.

---

## Module 3: Service Catalog, HMO Contracts, Accounting & Refunds

### Learning Objectives
- Maintain consultation SKUs, Senior/PWD statutory discounts (`RA 9994` / `RA 10754`), HMO contracts, and accounting journal mappings.

### Hands-On Steps
1. **Service Catalog (`/admin/services`):**
   - Create/verify `Psychiatric Initial Consultation (60 min)` and `Psychological Evaluation Battery`.
   - Confirm Senior Citizen / PWD 20% discount + VAT-exempt flags are enabled on eligible SKUs.
2. **HMO Contracts & Services (`/admin/hmo-contracts`, `/admin/hmo-services`):**
   - Map `Aventus` branch eligibility, LOA requirements, and contracted tariff rates.
3. **HMO Payer Review & Accounting (`/admin/hmo-payer-review`):**
   - Inspect **Accounting Status**, **Invoice Drafts**, **Invoice Document Terms**, and **Journal Account Mappings** (`/api/admin/hmo-journal-accounts`).
4. **Cancellation & Refund Rules (`/admin/cancellation-refunds`):**
   - Configure no-show / late-cancellation fee thresholds and dual-approval limits for refunds.

---

## Module 4: Clinical Governance, Supervision & Assessment Controls

### Learning Objectives
- Enforce `RA 10029` dual `RPm`+`RPsy` supervision rules, encounter approvers, and assessment catalog visibility.

### Hands-On Steps
1. **Supervision & Approvers (`/admin/supervision`, `/admin/clinical-note-approvers`, `/admin/encounter-approvers`):**
   - Pair `rpm.demo@example.test` with supervisor `rpsy.demo@example.test` so `RPm` evaluations require `RPsy` co-signature before release.
2. **Encounter Policies (`/admin/encounter-policies`):**
   - Verify `MHCLINIC-SOAP/3`, 14-Domain MSE, and `C-SSRS` screening triggers are enabled for initial psychiatric and therapy intakes.
3. **Assessments & MSE Tools (`/admin/assessments`, `/admin/mse-tools`):**
   - Verify the **68 `DSM-5-TR` Section III measures** are active and properly categorized by domain.

---

## Module 5: RA 10173 Privacy, Audit Logs, Exports & Report Studio

### Learning Objectives
- Monitor immutable audit logs, govern `break_glass` access, and enforce $k$-anonymity ($k \ge 5$) on reporting.

### Hands-On Steps
1. **Audit Log Review (`/admin/audit`):**
   - Filter by `MFA_FAILURE`, `ROLE_CHANGE`, and `BREAK_GLASS_ACCESS`.
   - Confirm every administrative change made in Modules 1–4 is logged with actor, timestamp, and target ID.
2. **Compliance Exports (`/admin/compliance-exports`):**
   - Generate a synthetic compliance audit bundle and verify no raw psychotherapy notes are leaked.
3. **Turnkey Reports & Report Studio (`/staff/reports`, `/admin/reports-studio`):**
   - Run `R01` (Utilization), `R28` (AR Aging, Clinician Payout & Accounting Reconciliation), and a Sponsor report (`R21`–`R25`).
   - Confirm small-cell suppression ($k \ge 5$) masks any cohort slice with fewer than 5 individuals.

---

## Module 6: Brand Portals, IHC Setup, Learning Hub & Helpline

### Learning Objectives
- Configure multi-brand portals, ADB IHC non-billable operating mode, `/learn` content, and `WP-31` safety routing.

### Hands-On Steps
1. **Brands & Landing Pages (`/admin/brands`, `/admin/brand-portals`, `/admin/landing-pages`):**
   - Inspect brand-specific operating mode (`billable_clinic` vs. `in_house_non_billable` for ADB IHC).
2. **IHC Setup (`/admin/ihc-workplan`, `/admin/ihc-roster`, `/admin/ihc-calendar-import`):**
   - Review roster import format and `.ics` calendar sync rules.
3. **Learning Hub & Risk Response (`/admin/learning-hub`, `/admin/risk-response`, `/admin/safety-followup-reviewers`):**
   - Confirm `/learn` psychoeducation modules are published and `L3`/`L4` helpline escalations route to active Safety Responders.

---

## Capstone: End-to-End Branch Launch Verification

To pass Admin Certification, complete the following without supervisor intervention:
1. Provision 1 synthetic branch, 2 rooms, and 3 clinicians (`MD`, `RPsy`, `RPm`) with valid synthetic credentials.
2. Confirm an `RPm` **cannot** prescribe (`RA 6675`) or unilaterally release a psychological evaluation (`RA 10029`).
3. Confirm an Aventus HMO visit passes all 8 scheduling gates and maps cleanly to an invoice draft in `/admin/hmo-payer-review`.
4. Locate all configuration actions in `/admin/audit` and verify $k \ge 5$ suppression in `/staff/reports`.
5. Sign off all readiness items in the [Content & Data Onboarding Checklist](02-content-and-data-onboarding-checklist.md).
