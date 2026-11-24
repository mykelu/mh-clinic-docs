# Frequently Asked Questions

> **Navigation:** [Knowledge Base Home](README.md) · [Getting Started](GETTING_STARTED.md) · [Glossary](GLOSSARY.md)
>
> **Doc ID:** `MHD-REF-03` · **Type:** Reference · **Audience:** Everyone · **Revised:** 25 November 2026 · All examples use synthetic data.

## About the platform

**What is MH-Clinic?**
A multi-tenant platform for mental health, integrative medicine and institutional counseling. It covers scheduling, clinical documentation, billing and HMO operations, and reporting. See the [Executive Deck](decks/01-executive-introduction-deck.md).

**Can one company run several brands?**
Yes. Brands sit under a governed company tree with separate client records, consent and intake. The example brands in these docs are MindWell.PH (self-pay/hybrid), Aventus (HMO-backed) and ABC Bank (in-house counseling). See [Manual 10](manuals/10-saas-clients-and-tenant-onboarding.md).

**Is the data in these docs real?**
No. Every screenshot, persona and lab uses synthetic data, such as `@example.test` addresses.

## Access and security

**How do staff sign in?**
Through verified Google Workspace sign-in or invitation-based staff credentials, followed by mandatory MFA (authenticator app or passkey). See [Manual 01](manuals/01-getting-started-and-mfa.md).

**Does signing in give me access to clinic data?**
No. An administrator must grant an explicit role for a specific company and brand. Clinicians also complete readiness steps before they can be booked.

**Can administrators or coordinators read clinical notes?**
No. Administrative, coordinator, HMO and AI roles are blocked from clinical notes, prescriptions and diagnoses at the database layer. See [Persona 01](personas/01-company-and-branch-administrator.md) and the [Engineering Deck](decks/02-engineering-and-developer-deck.md).

**How do I report a security vulnerability?**
Privately, as described in [SECURITY.md](SECURITY.md). Never open a public issue with real data or credentials.

**Who handles privacy requests?**
The Data Protection Officer: see [SECURITY.md](SECURITY.md#privacy-and-data-protection-officer).

## Clinical work

**Who can sign a prescription?**
Only a verified psychiatrist. Coordinators can prepare drafts for review. See [Manual 03](manuals/03-clinical-workflows-and-prescribing.md).

**How are suicide-risk screens handled?**
`C-SSRS` positive screens flow to risk triage and the professional follow-up worklist, alongside a collaborative safety plan. See [Manual 03](manuals/03-clinical-workflows-and-prescribing.md) and [Persona 07](personas/07-case-manager-and-safety-responder.md).

**Which assessments are available?**
The catalog includes 68 `DSM-5-TR` Section III measures, plus dual `RPm` + `RPsy` evaluation reports. See [Manual 04](manuals/04-assessments-and-specialty-tracks.md).

**How does a client verify a certificate?**
Issued certificates carry a QR code that opens a public verification page without exposing clinical text. See [Manual 03](manuals/03-clinical-workflows-and-prescribing.md).

## Billing and reporting

**Does it support HMO billing?**
Yes. The Aventus workflow covers referral, LOA hold, encounter, SOA, sales invoice and BIR 2307 settlement. See [Manual 02](manuals/02-scheduling-and-hmo-operations.md) and [Manual 08](manuals/08-accounting-invoicing-and-payouts.md).

**What reports are included?**
Thirty turnkey reports (`R01`–`R30`), role-scoped dashboards and a no-code Report Studio. Aggregates below a cohort floor (`k ≥ 5`) are suppressed. See [Manual 06](manuals/06-reporting-and-analytics-guide.md).

## Training

**Where do I practise?**
In a synthetic training tenant, using the [Role Exercises & Labs](training/01-role-exercises-and-labs.md). Administrators have their own [curriculum](training/03-admin-training-curriculum.md).

**Do these docs replace my clinic's procedures?**
No. Your clinic's own standard operating procedures take precedence.

**Is there a Filipino or Taglish version?**
Not yet in this public knowledge base.

---

[Knowledge Base Home](README.md) · [Getting Started](GETTING_STARTED.md) · [Glossary](GLOSSARY.md)
