# MH-Clinic: Clinical & Operations User Walkthrough Deck

> **Navigation:** [Knowledge Base Home](../README.md) · [Master Index](../INDEX.md) · [Glossary](../GLOSSARY.md) · [Operations Manuals](../manuals/02-scheduling-and-hmo-operations.md)

> **Audience:** Coordinators, Psychiatrists, Psychologists, Psychometricians, Counselors, Specialty Clinicians, and Billing Officers

---

## Slide 1: The Unified Patient & Operational Journey

```mermaid
flowchart LR
  A["1. Inquiry / Referral\n/staff/inquiries\n/staff/hmo-requests"] --> B["2. 8-Gate Booking\n/staff/appointments\n/staff/waitlist"]
  B --> C["3. Client Preparation\nConsent, Intake, PHQ-9/GAD-7\n/client/[brand]"]
  C --> D["4. Consultation\nSOAP / 5Ps, MSE, eRx, MedCert\n/professional/schedule, /telehealth/[appointmentId]"]
  D --> E["5. Billing / Settlement\nSOA, Sales Invoice, BIR 2307\n/staff/payments, /hmo"]
  E --> F["6. BI & Quality\nR01–R30 & Report Studio\n/staff/reports, /admin/ihc-workplan"]
```

---

## Slide 2: Front-Desk & HMO Operations

![8-Gate Booking Simulator and 7-Step Aventus HMO Workflow](../assets/visuals/eight-gate-booking-flow.svg)

- **Booking with Confidence:** The 8-Gate Booking Simulator explains *why* a slot is open or blocked (location, room, equipment, notice window, hours, or eligibility).
- **Aventus 7-Step HMO Flow:** Paste referral slip $\rightarrow$ reserve LOA slot $\rightarrow$ confirm $\rightarrow$ track in 10-column Inventory Ledger $\rightarrow$ generate branded `SOA` & `Sales Invoice` (`10% WTax`) $\rightarrow$ settle with Deposit Slip + `BIR 2307`.
- **Smart Waitlist & AI Co-Pilot:** Backfill cancelled slots (`/staff/waitlist`) or review `AG-UI` draft actions (`/staff/ai-coordinator`) with 1-click human approval.

---

## Slide 3: Clinician Encounter Workspace
- **Fast, Structured Notes (`MHCLINIC-SOAP/3`):** Apply `"Normal Baseline (WNL)"` in 1 click, toggle abnormal MSE chips, and pick `ICD-10-CM` (`1,204` codes) or `ICD-11` (`661` codes) with 1-line descriptions.
- **Safe Prescribing (`eRx`):** Generic-first format (`Generic Name (Brand Name)` per RA 6675), DDB `S2` controlled drug checks, and metabolic/`QTc`/`AIMS`/`ANC` monitoring flowsheets.
- **Assessments (`WP-17` & `WP-24`):** Browse 68 standardized `DSM-5-TR` Section III measures (`/staff/assessments/dsm5tr`), track longitudinal `PHQ-9`/`GAD-7` progress, and co-sign dual `RPm` + `RPsy` evaluation reports.

![DSM-5-TR Standard Assessment Measures catalog displaying all 68 measures with category and population filters](../assets/screenshots/assessments-dsm5tr-catalog.png)

*Synthetic clinician-training capture, November 2026.*

---

## Slide 4: ABC Bank In-House Counseling (`IHC`) & Crisis Helpline
- **IHC Workspace (`/admin/ihc-workplan`, `/professional/ihc`):** Switchable `SOAP <-> 5Ps` formulation, `MMDDYYYY+Initials+MMDDYYYY` client codes, `XXX / 4,000` reach counter, and 1-click `R14`–`R21` turnkey reports.
- **Anonymous Helpline (`/helpline`, `/staff/helpline-desk`):** Entitlement-gated access with a corporate passcode or blinded member token, then zero-PII `ANON-xxxx` sessions with `L1`–`L4` triage, automatic 15-minute post-`L1` responder cooldown, and curated self-reading guides (`/learn`).

![ABC Bank 2026 Institutional Workplan showing R14–R21 links and Withheld for privacy suppression](../assets/screenshots/abc-bank-ihc-workplan.png)

*Synthetic administrator-training capture, November 2026.*

---

## Slide 5: Reporting & Analytics (`R01`–`R30`)

![BI Dashboards, R01–R30 Turnkey Report Suite, and k-Anonymity Governance Map](../assets/visuals/bi-30-reports-map.svg)

- **30 Turnkey Reports:** Covering Executive Utilization (`R01`–`R05`), Clinical Governance (`R06`–`R13`), Official ABC Bank IHC Suite (`R14`–`R21`), HMO/Sponsor (`R22`–`R24`), and Commercial Finance/NPS (`R25`–`R30`).
- **Privacy First:** Small cohorts ($< 5$ clients) are automatically suppressed so aggregate reports never expose individuals.

![Internal Report Explorer displaying scoped inquiry counts, chart bars, UTC timestamp, and CSV/print exports](../assets/screenshots/report-explorer-inquiries.png)

*Synthetic operations-training capture, November 2026.*
