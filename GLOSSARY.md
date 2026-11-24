# Glossary

> **Navigation:** [Knowledge Base Home](README.md) · [Master Index](INDEX.md) · [Visual Guide](VISUAL_GUIDE.md)
>
> **Doc ID:** `MHD-REF-01` · **Type:** Reference · **Revised:** 25 November 2026

Terms used across the manuals, persona guides, training labs, and decks. Route paths match the application on `mh-clinic` `main` (`cf52f970`).

## A–C

| Term | Meaning |
| :--- | :--- |
| **5Ps** | Formulation lens (presenting, precipitating, predisposing, perpetuating, protective) paired with `SOAP` in institutional notes. |
| **8-Gate Simulator** | Pre-booking validator for hours, shift, room, credential match, buffer, double-booking, HMO eligibility, and age/consent. Administrators run it from `/admin/configuration#booking-simulator`; live booking is at `/staff/appointments`. |
| **ADIME** | Nutrition Care Process note: assessment, diagnosis, intervention, monitoring, and evaluation. Documented in `/professional/appointments/[appointmentId]/nutrition-chart`. |
| **AG-UI** | Human-in-the-loop AI coordinator workspace at `/staff/ai-coordinator`. |
| **ANON-xxxx** | Ephemeral helpline session identifier issued after a valid entitlement token. It is not a legal name or login account. |
| **Aventus** | HMO / payer workflow covering LOA, visit verification, SOA/SI, and BIR 2307 remittance. |
| **Brand portal** | White-label public site at `/sites/[company]/[target]`. Clients sign in at `/client-access/[brand]` and work in `/client/[brand]`. |
| **C-SSRS** | Columbia-Suicide Severity Rating Scale. Positive screens feed `/staff/risk-triage` and `/professional/safety-followup`. |
| **CAS / `expectedRevision`** | Compare-and-swap revision token used to prevent conflicting clinical writes. |
| **CMA** | Certified Medical Acupuncturist — the acupuncture specialty track (`WP-28`) in the specialty manuals. |

## D–I

| Term | Meaning |
| :--- | :--- |
| **DSM-5-TR catalog** | The 68-measure APA Section III catalog at `/staff/assessments/dsm5tr`. Assignment and review use `/staff/assessments` and `/professional/assessments`. |
| **Entitlement gate** | Helpline access control at `/helpline`. A corporate passcode or blinded member token opens an `ANON-xxxx` session. Unentitled visitors see the national crisis deflection card only. |
| **eRx** | Electronic prescription under RA 6675 (Generics Act), prepared from the professional appointment note or `/staff/prescription-drafts`. |
| **IHC** | In-house counseling (institutional, typically non-billable). Counselors use `/professional/ihc`; coordinators use `/staff/ihc`. |
| **k-anonymity** | Disclosure floor for sponsor and institutional reports (`k ≥ 5` unless a higher clinic floor applies). Small cells are suppressed. |
| **L1–L4** | Helpline acuity bands. `L1` is imminent life safety; `L4` is informational or self-guided. After an `L1` session the responder desk enforces a 15-minute cooldown. |
| **LOA** | Letter of authorization from an HMO payer, tracked through `/staff/hmo-requests`. |

## M–R

| Term | Meaning |
| :--- | :--- |
| **MBC** | Measurement-based care: repeated scored instruments such as PHQ-9 and GAD-7. |
| **MDT** | Multidisciplinary team coordination, managed as case episodes at `/case-manager/episodes`. |
| **MedCert** | QR-verified medical or fit-to-work certificate. Public authenticity checks use `/verify/document/[token]`. |
| **MFA** | Multi-factor authentication. Staff enroll TOTP or passkeys at `/mfa/setup`, `/mfa/passkeys`, and `/mfa/verify`. |
| **MSE** | Mental status examination. The 14-domain structured exam lives in `/professional/appointments/[appointmentId]/notes`. |
| **PHI** | Personal health information. Training materials in this repository use synthetic data only. |
| **PRC / PTR / S2** | Professional license, tax receipt, and dangerous-drug authority records, maintained at `/admin/professional-credential-validity`. |
| **RA 10173** | Philippine Data Privacy Act of 2012. |
| **RA 10029** | Philippine Psychology Act: dual `RPm` + `RPsy` evaluation release rules. |
| **RA 6675** | Philippine Generics Act: generic-first prescribing. |
| **RLS** | PostgreSQL row-level security isolating company and brand data. |
| **R01–R30** | Turnkey operational and institutional reports, opened from `/staff/reports` or `/admin/reports-studio`. |
| **RPm / RPsy** | Registered Psychometrician and Registered Psychologist. |
| **RND** | Registered Nutritionist-Dietitian. |

## S–Z

| Term | Meaning |
| :--- | :--- |
| **SOAP** | Subjective, objective, assessment, plan. The versioned clinic note is `MHCLINIC-SOAP/3`. |
| **SOA / SI / BIR 2307** | Statement of account, sales invoice, and withholding tax certificate in the HMO settlement path. |
| **Sponsor portal** | Employer or HR aggregate view at `/sponsor-access/[company]/[brand]`. It does not expose individual clinical charts. |
| **Staff SOP** | Day-to-day staff procedures live in the internal operator documentation. This public knowledge base is the showcase manual set. |
| **Synthetic data** | Invented training records such as `patient.demo@example.test` or `ANON-9042`. Never use real patient or live credential data here. |
| **Telehealth room** | Appointment-scoped session at `/telehealth/[appointmentId]`. Clients also prepare from `/client/[brand]/appointments/[appointmentId]/prepare`. |
| **WP-01–WP-32** | Work packages delivered across six waves. See the [Master Index](INDEX.md). |
