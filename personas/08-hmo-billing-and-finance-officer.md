# Persona Guide 08: HMO Billing & Finance Officer

> **Navigation:** [Knowledge Base Home](../README.md) · [Master Index](../INDEX.md) · [Scheduling & HMO Operations](../manuals/02-scheduling-and-hmo-operations.md) · [Reporting & Analytics](../manuals/06-reporting-and-analytics-guide.md) · [Role Exercises & Labs](../training/01-role-exercises-and-labs.md) · [Glossary](../GLOSSARY.md)
>
> **Doc ID:** `MHD-PER-08` · **Type:** How-to guide · **Audience:** The named role · **Revised:** 25 November 2026 · All examples use synthetic data.

---

## 1. Role Summary & Scope

The **HMO Billing & Finance Officer** (`BILLING` / `FINANCE`) manages point-of-sale self-pay collections, **Senior Citizen (`RA 9994`) / PWD (`RA 10754`)** statutory discounts, **7-Step Aventus HMO** claim packets, reconciliation, and revenue/aging analytics (`R11`–`R15`).

| Dimension | Details |
| :--- | :--- |
| **Primary Workspaces** | `/staff/payments`, `/admin/hmo-payer-review`, `/staff/reports/ar-payout-reconciliation`, `/staff/reports` |
| **Core Work Packages** | `WP-15` Aventus HMO Workflow, `WP-25` Self-Pay, Senior/PWD, Revenue & AR Reconciliation, `WP-30` Financial Reports |
| **Data Visibility** | Invoices, LOAs, `ICD-10` billing codes (when consented for HMO), payments, refunds; **no access** to psychotherapy narrative notes |

---

## 2. Core Workflows

### 2.1 Self-Pay Checkout & Statutory Discounts (`WP-25`)
1. Open **`/staff/payments`** for completed encounters.
2. Verify line items against the Branch Service Catalog.
3. When a valid **Senior Citizen (`RA 9994`)** or **PWD (`RA 10754`)** ID is verified:
   - System automatically strips **12% VAT** (VAT-exempt) and applies the **20% statutory discount** on eligible services/medications.
   - Audit log records the ID reference and cashier approval.
4. Accept payment (`CASH`, `CARD`, `GCASH/MAYA`, `BANK_TRANSFER`) and issue official receipt.

### 2.2 Aventus HMO Claim Assembly & Submission (`WP-15`)
1. Filter **`/admin/hmo-payer-review`** for encounters marked `SIGNED` by the clinician.
2. Confirm all **7 Aventus HMO steps** are complete:
   - Valid Member ID & active policy
   - Benefit cap check
   - Valid LOA number & date range
   - Attached LOA document
   - Co-pay collected (if any)
   - Clinician attestation (`SIGNED` encounter)
   - Billing `ICD-10` code (with RA 10173 HMO disclosure consent)
3. Export or submit the claim batch and track status (`SUBMITTED` → `IN_REVIEW` → `PAID` / `DENIED`).

### 2.3 Aging, Denials & Reconciliation (`/staff/reports/ar-payout-reconciliation`)
- Run **`R11`–`R15`** weekly in `/staff/reports` to monitor:
  - Daily collections & payment method mix
  - HMO AR aging (`0-30`, `31-60`, `61-90`, `90+` days)
  - Denial reason codes (missing LOA, expired LOA, unsigned encounter)
- Process void/refund requests with **Supervisor Dual-Approval** for amounts exceeding branch thresholds.

---

## 3. Visual Workspace Reference

![Accounting approval dialog showing the synthetic book, journal amount, reason field, and Approve journal action](../assets/screenshots/accounting-review-journal-approval.png)

*Synthetic operator-training capture, November 2026. Approvers verify book, date, amount, and audit reason before approving a journal draft.*

![Reconciliation and close workspace listing readiness checks and audited close and reopen history](../assets/screenshots/accounting-period-readiness.png)

*Synthetic operator-training capture, November 2026. Confirm zero unposted journals and zero unmatched bank lines before closing the period.*

![Accounting Transactions and reports screen showing guided transaction entry and PHP cash flow summary](../assets/screenshots/accounting-cash-flow.png)

*Synthetic operator-training capture, November 2026. Verify book, date range, and branch scope before exporting financial summaries.*

---

## 4. Practice & Verification
- Complete **Lab 08** in [Role Exercises & Labs](../training/01-role-exercises-and-labs.md).
- Review full billing rules in [Manual 02: Scheduling & HMO Operations](../manuals/02-scheduling-and-hmo-operations.md) and [Manual 08: Accounting, Invoicing & Journal Mapping](../manuals/08-accounting-invoicing-and-payouts.md).

---

← Previous: [Persona Guide 07: Case Manager & Safety Responder](07-case-manager-and-safety-responder.md) · [Knowledge Base Home](../README.md) · [Getting Started](../GETTING_STARTED.md) · [FAQ](../FAQ.md) · Next: [Persona Guide 09: Client, Patient & Guardian](09-client-patient-and-guardian.md) →
