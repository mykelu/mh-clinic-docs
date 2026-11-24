# MH-Clinic Knowledge Base Index (`A–Z` & Route Map)

> **Doc ID:** `MHD-REF-02` · **Type:** Reference · **Revised:** 25 November 2026

This index maps every major **route**, **work package (`WP-01`–`WP-32`)**, **turnkey report (`R01`–`R30`)**, and **compliance control** to its manual and persona guide.

> **Navigation:** [Knowledge Base Home](README.md) · [Glossary](GLOSSARY.md) · [Visual Guide](VISUAL_GUIDE.md)

---

[Visual Guide](VISUAL_GUIDE.md): Find screenshots by task. [Glossary](GLOSSARY.md) defines the shared vocabulary used in the manuals and labs.

## Start Here

| Document | Purpose |
| :--- | :--- |
| [Getting Started](GETTING_STARTED.md) | Reading paths by role and time available |
| [FAQ](FAQ.md) | Common questions about the platform, access, clinical work, billing and training |
| [Document Register](DOCUMENT_REGISTER.md) | Every document with its ID and type |
| [Accessibility](ACCESSIBILITY.md) | Accessibility statement and checklist |
| [Contributing](CONTRIBUTING.md) | Style guide and rules for changes |
| [Changelog](CHANGELOG.md) | What changed and when |

## 1. Work Package Index (`WP-01` – `WP-32`)

| Wave | Work Packages | Primary Documentation |
| :--- | :--- | :--- |
| **Wave 0** (`WP-01`–`WP-10`) | Core platform, policy alignment, Postgres CI, CAS, WCAG 2.2 AA | [Developer Deck](decks/02-engineering-and-developer-deck.md) · [Getting Started](manuals/01-getting-started-and-mfa.md) |
| **Wave 1** (`WP-11`–`WP-15`) | 6-layer Policy Engine, 8-Gate Simulator, Care Pathways, 5 Admin Hubs, 7-Step Aventus HMO | [Scheduling & HMO](manuals/02-scheduling-and-hmo-operations.md) · [Admin Guide](personas/01-company-and-branch-administrator.md) |
| **Wave 2** (`WP-16`–`WP-20`) | $k$-Anonymous Sponsor Portal, Longitudinal MBC, Brand CMS, Sandbox, SaaS Entitlements | [Sponsor Guide](personas/10-sponsor-and-hr-viewer.md) · [Admin Guide](personas/01-company-and-branch-administrator.md) |
| **Wave 3** (`WP-21`–`WP-25`) | 14-Domain MSE & `ICD-10-CM`/`ICD-11`, `C-SSRS` Safety Plan, RA 6675 `eRx`, Dual `RPm`+`RPsy`, Self-Pay & PH Senior/PWD | [Clinical Workflows](manuals/03-clinical-workflows-and-prescribing.md) · [Assessments](manuals/04-assessments-and-specialty-tracks.md) |
| **Wave 4** (`WP-26`–`WP-30`) | `Lifestyle Rx` & Metabolic/`QTc`/`AIMS`/`ANC`, QR `MedCerts`, `MD`/`RND`/`CMA` tracks, ABC Bank `IHC` OS, `R01`–`R30` + Report Studio | [ABC Bank IHC Manual](manuals/05-ihc-and-case-management.md) · [BI & Reports](manuals/06-reporting-and-analytics-guide.md) |
| **Wave 5** (`WP-31`–`WP-32`) | Anonymous Helpline, Psychoeducation/Learning Hub, `AG-UI` AI Coordinator, Native Telehealth + Ambient Scribe | [Helpline, Learn & AI](manuals/07-helpline-learning-hub-and-ai-coordinator.md) |

---

## 2. Application Route Directory

### Client, Public & Self-Service Routes
- `/helpline` — Entitlement-gated anonymous helpline & national crisis hotline deflection ([Manual 07](manuals/07-helpline-learning-hub-and-ai-coordinator.md))
- `/learn` — Public psychoeducation library & self-reading blog hub ([Manual 07](manuals/07-helpline-learning-hub-and-ai-coordinator.md))
- `/client-access/[brand]` — Client and guardian sign-in for a brand portal ([Client Guide](personas/09-client-patient-and-guardian.md))
- `/client/[brand]` — Client portal dashboard & assigned assessment tasks ([Client Guide](personas/09-client-patient-and-guardian.md))
- `/sponsor-access/[company]/[brand]` — Sponsor and HR aggregate dashboard with $k$-anonymity ([Sponsor Guide](personas/10-sponsor-and-hr-viewer.md))
- `/client/[brand]/evaluation-reports` — Feedback-gated dual-signed psychological evaluation PDFs ([Manual 04](manuals/04-assessments-and-specialty-tracks.md))
- `/client/[brand]/lifestyle-rx` & `/client/[brand]/nutrition-summary` — Client care plans & summaries ([Manual 04](manuals/04-assessments-and-specialty-tracks.md))
- `/verify/document/[token]` — Public QR verification for `eRx` and `MedCert`/`Fit-to-Work` ([Manual 03](manuals/03-clinical-workflows-and-prescribing.md))

### Staff, Coordinator & Clinical Routes
- `/staff` & `/staff/appointments` — Coordinator queue & 8-Gate booking ([Coordinator Guide](personas/02-front-desk-coordinator.md))
- `/staff/assessments/dsm5tr` — 68-measure APA DSM-5-TR Section III standard catalog ([Manual 04](manuals/04-assessments-and-specialty-tracks.md))
- `/staff/helpline-desk` — `L1`–`L4` crisis responder console & 15-minute post-`L1` cooldown ([Manual 07](manuals/07-helpline-learning-hub-and-ai-coordinator.md))
- `/staff/ai-coordinator` — Omnichannel `AG-UI` AI Virtual Care Coordinator ([Manual 07](manuals/07-helpline-learning-hub-and-ai-coordinator.md))
- `/telehealth/[appointmentId]` — Native telehealth room & dual-consent ambient scribe ([Manual 07](manuals/07-helpline-learning-hub-and-ai-coordinator.md))
- `/professional/appointments/[appointmentId]/notes` — `MHCLINIC-SOAP/3` (`SOAP <-> 5Ps`), 14-domain MSE, `ICD-10-CM`/`ICD-11` ([Manual 03](manuals/03-clinical-workflows-and-prescribing.md))
- `/professional/evaluations/instruments` & `/professional/evaluations/report` — `RPm` + `RPsy` evaluation suite ([Psychologist Guide](personas/04-psychologist-and-psychometrician.md))
- `/case-manager/episodes` — Longitudinal MDT case management ([Case Manager Guide](personas/07-case-manager-and-safety-responder.md))

- `/staff/inquiries`, `/staff/professional-matching`, `/staff/outreach`, `/staff/corporate-events` — CRM inquiry pipeline, clinician matching, outreach & corporate events ([Manual 09](manuals/09-crm-inquiries-and-outreach.md))

### Administration, Accounting, IHC & BI Reporting Routes
- `/admin/configuration/formulary` & `/admin/configuration/prescription-authority` — 1-click PH Psychiatric Starter Formulary & clinical approval ([Manual 03](manuals/03-clinical-workflows-and-prescribing.md))
- `/admin/hmo-payer-review`, `/admin/cancellation-refunds`, `/staff/payments`, `/staff/reports/ar-payout-reconciliation` — HMO invoicing, journal accounts, refunds & `R28` reconciliation ([Manual 08](manuals/08-accounting-invoicing-and-payouts.md))
- `/admin/learning-hub` — Psychoeducation & blog publisher ([Manual 07](manuals/07-helpline-learning-hub-and-ai-coordinator.md))
- `/admin/ihc-workplan` & `/admin/ihc-roster` — ABC Bank IHC OS & `R14`–`R21` reports ([Manual 05](manuals/05-ihc-and-case-management.md))
- `/staff/reports` & `/admin/reports-studio` — Executive/Clinical/Commercial reports (`R01`–`R30`) & No-Code Report Studio ([Manual 06](manuals/06-reporting-and-analytics-guide.md))
- `/admin/organization-structure`, `/admin/brands/new-wizard`, `/admin/brand-portals`, `/sites/[company]/[target]` — SaaS tenant provisioning, entitlements (`WP-20`) & white-label brand launch ([Manual 10](manuals/10-saas-clients-and-tenant-onboarding.md))
- `/admin/configuration/*` — 6-layer policy registry, specialty track protocols, statutory sales & technical reference ([Manual 11](manuals/11-configurations-and-reference.md))

---

## 3. Compliance & Regulatory Reference Map

| Regulation / Standard | Where Enforced | Documentation |
| :--- | :--- | :--- |
| **RA 10173 (PH Data Privacy Act)** | PostgreSQL RLS, Zero-PII helpline, $k \ge 5$ anonymity | [Developer Deck](decks/02-engineering-and-developer-deck.md) · [Manual 06](manuals/06-reporting-and-analytics-guide.md) |
| **RA 6675 (PH Generics Act) & DDB S2** | Generic-first `eRx` + controlled substance safeguards | [Manual 03](manuals/03-clinical-workflows-and-prescribing.md) · [Psychiatrist Guide](personas/03-psychiatrist-and-prescriber.md) |
| **RA 10029 (PH Psychology Act)** | Dual `RPm` + `RPsy` PRC/PTR signatures & feedback lock | [Manual 04](manuals/04-assessments-and-specialty-tracks.md) · [Psychologist Guide](personas/04-psychologist-and-psychometrician.md) |
| **RA 9994 / RA 10754 (Senior & PWD)** | 20% discount + 12% VAT exemption calculator | [Manual 02](manuals/02-scheduling-and-hmo-operations.md) · [Finance Guide](personas/08-hmo-billing-and-finance-officer.md) |

---

← Previous: [Glossary](GLOSSARY.md) · [Knowledge Base Home](README.md) · [Getting Started](GETTING_STARTED.md) · [FAQ](FAQ.md) · Next: [Visual Guide](VISUAL_GUIDE.md) →
