# Manual 02: Scheduling, Waitlist & 7-Step Aventus HMO Operations

## 1. 8-Gate Booking Simulator & Planned Hours (`WP-12`)
Before confirming any appointment, the **8-Gate Booking Simulator** evaluates:
1. Active company & brand scope
2. Active service & delivery mode (`in_person` vs. `teleconsult`)
3. Active location, room, and equipment availability (buffer-aware)
4. Clinician 6/6 readiness & brand assignment
5. Published planned hours / calendar capacity block
6. Time-off & holiday exclusions
7. Booking notice & cutoff windows (`24h` default, policy-driven)
8. Payer / referral / bundle / statutory eligibility

Administrators can promote draft planned hours to bookable calendar capacity in 1 click from `/admin/configuration/schedules`.

### When the booking panel shows no published hours

![Staff booking panel showing a disabled Book pending confirmation button and a no-published-hours notice](../assets/screenshots/booking-unpublished-hours.png)

*Synthetic operator-training capture, November 2026. If this notice appears, check your selected brand, professional and booking method. Choose another option or ask an administrator to review published hours.*

## 2. Smart Waitlist Backfill (`WP-27`, `R29`)
- When a confirmed appointment is cancelled, `/staff/waitlist` surfaces ranked waitlisted clients matching the clinician, service, mode, and time preference.
- Staff (or the `WP-32` AI Coordinator in `HITL` mode) can offer the vacated slot with a bounded hold expiry, tracked by `R29` Waitlist Backfill & Recovery.

## 3. 7-Step Aventus HMO Workflow (`WP-15`)
1. **Referral Capture (`/staff/hmo-requests`):** Paste the 8-field Aventus referral slip; system validates LOA number, validity window, and covered service.
2. **Slot Hold & Clinic Confirmation:** Link the referral to a calendar slot and confirm attendance.
3. **10-Column Inventory Ledger:** Tracks referral $\rightarrow$ LOA $\rightarrow$ encounter $\rightarrow$ closeout status (`R22` HMO LOA-to-Encounter Conversion).
4. **LOA Amendment Loop:** Request/record payer-approved schedule or clinician changes without losing audit lineage (`/staff/hmo-rescheduling`).
5. **Encounter & Clinical Output:** Clinician attests `served` and completes `SOAP` + `MedCert`/`eRx`; HMO staff see completion booleans only.
6. **Branded `SOA` & `Sales Invoice` (`/hmo/statements`):** Generates 100% Brand-Identity-driven `Statement of Account` (privacy-safe client initials) and `Sales Invoice` with **10% Withholding Tax (`WTax`)** and `Net Payable`.
7. **Settlement & `BIR 2307`:** Record AUB deposit slip + `BIR Form 2307` certificate; feeds `R25` Tiered Volume (`1–20`, `21–30`, `31+`) and `R28` AR Aging.

## 4. Self-Pay Memberships, Bundles & Senior/PWD Statutory Discounts (`WP-25`)
- `/staff/clients/[clientId]/memberships` manages recurring memberships and prepaid care bundles (deferred revenue rollforward in `R27`).
- **PH Senior Citizen (`RA 9994`) & PWD (`RA 10754`):** Built-in statutory calculator applies **20% discount + 12% VAT exemption** with verified ID evidence at checkout.
