# Gabay ng Persona 09: Client, Pasyente at Guardian (Filipino / Taglish Draft)

> **Navigation:** [Knowledge Base Home](../README.md) · [English Guide (Persona 09)](09-client-patient-and-guardian.md) · [Pagsisimula (Taglish Draft)](../GETTING_STARTED_FIL.md) · [Manual 07: Helpline & Learning Hub](../manuals/07-helpline-learning-hub-and-ai-coordinator.md) · [Glossary](../GLOSSARY.md)
>
> **Doc ID:** `MHD-PER-11` · **Type:** How-to guide · **Audience:** Client, Patient & Authorized Guardian (Filipino / Taglish) · **Revised:** 25 November 2026 · All examples use synthetic data.

> [!IMPORTANT]
> **Draft translation — needs native-speaker review before publication.** Ang pahinang ito ay Taglish/Filipino draft ng [Persona Guide 09](09-client-patient-and-guardian.md). Ang mga legal at privacy notice tungkol sa `RA 10173` (Data Privacy Act of 2012) ay dapat kumpirmahin sa abogado o sa Data Protection Officer (`dpo@cml-intl.com`). Lahat ng halimbawa ay gumagamit ng **synthetic data lamang**.

---

## 1. Ano ang magagawa mo sa Client Portal

Ang **Client, Pasyente, at Authorized Guardian** (`PATIENT` / `GUARDIAN`) ay gumagamit ng **Client Sign-In** (`/client-access/[brand]`), **Client Portal** (`/client/[brand]`), **Telehealth room** (`/telehealth/[appointmentId]`), **Learning Hub** (`/learn`), at ng entitlement-gated na **Anonymous Helpline** (`/helpline`).

| Bahagi | Detalye |
| :--- | :--- |
| **Pangunahing pages** | `/client-access/[brand]`, `/client/[brand]`, `/client/[brand]/appointments/[appointmentId]/prepare`, `/client/[brand]/certificate-verifications`, `/client/[brand]/evaluation-reports`, `/client/[brand]/lifestyle-rx`, `/telehealth/[appointmentId]`, `/learn`, `/helpline` |
| **Mga saklaw na module** | `WP-18` Client Portal, `WP-32` Telehealth, `WP-24` Pre-Visit Assessments, `WP-26` Lifestyle Rx, `WP-31` Helpline at `/learn` |
| **Karapatan sa privacy** | Kontrol sa pahintulot alinsunod sa `RA 10173` (confirm with a lawyer or the DPO), guardian access para sa menor de edad, at walang paglabas ng clinician-only process notes |

---

## 2. Mga hakbang para sa client at guardian

### 2.1 Pamahalaan ang appointment at paghahanda bago ang session (`/client/[brand]`)
1. Buksan ang `/client-access/[brand]` at mag-sign in gamit ang iyong verified access link o account.
2. Tingnan ang iyong mga darating na in-person o telehealth appointment sa `/client/[brand]`.
3. Sagutan ang digital **Consent to Care** at **RA 10173 Privacy Notice** bago ang iyong unang konsultasyon.
4. Para sa telehealth visit (kung naka-enable sa iyong clinic brand), piliin ang **Join Telehealth** 10 minuto bago ang oras at i-check ang iyong camera at microphone.

### 2.2 Sagutan ang pre-visit questionnaires (`/client/[brand]`)
1. Buksan ang mga naka-assign na questionnaire bago ang iyong session.
2. Piliin ang **Save** para itabi ang sagot o **Submit** para makita ng iyong clinician ang iyong progreso bago magsimula ang konsultasyon.

### 2.3 Tingnan ang reseta, medical certificate, at Lifestyle Rx
- I-download ang mga pirmadong **RA 6675 Electronic Prescriptions** at **QR-Verified Medical Certificates** sa `/client/[brand]/certificate-verifications`.
- Sundan ang iyong **6-Pillar Lifestyle Rx** plan (tulog, nutrisyon, ehersisyo, mindfulness) sa `/client/[brand]/lifestyle-rx`.

### 2.4 Guardian o proxy access para sa menor de edad
- Ang magulang o legal guardian na naka-link sa verified **Guardian Relationship** ay maaaring mag-manage ng schedule, consent, at pediatric forms ng menor de edad.
- Nirerespeto ang mga patakaran sa adolescent confidentiality kung kinakailangan ng clinician at batas (confirm with a lawyer or the DPO).

### 2.5 Anonymous Helpline (`/helpline`) at Learning Hub (`/learn`)
- **Kailangan mo ba ng agarang kausap sa oras ng krisis?**
  - Kung nasa agarang panganib, tumawag agad sa **911** o sa mga verified Philippine National Crisis Hotlines sa [Manual 07](../manuals/07-helpline-learning-hub-and-ai-coordinator.md#verified-philippine-national-crisis-hotlines-checked-25-november-2026-pht) (**NCMH 1553**, **In Touch**, **Hopeline PH** — verified 25 November 2026 PHT; pending clinical reviewer confirmation).
  - Kung may corporate passcode o blinded member token ang iyong organisasyon at naka-enable ang `/helpline`, maaari kang pumasok nang anonymous (`ANON-xxxx`) nang hindi nagbibigay ng legal name, email, o mobile number.
- **Gusto mo bang magbasa ng self-guided mental health guides?**
  - Buksan ang **`/learn`** kahit walang login para sa mga gabay tulad ng CBT thought records, sleep reset, at 5-4-3-2-1 grounding exercises.

---

## 3. Pagsasanay at karagdagang gabay

- Para sa synthetic hands-on practice, tingnan ang **Lab 09** sa [Role Exercises & Labs](../training/01-role-exercises-and-labs.md).
- Para sa kumpletong English reference at screenshots, buksan ang [Persona Guide 09 (English)](09-client-patient-and-guardian.md) at [Manual 07](../manuals/07-helpline-learning-hub-and-ai-coordinator.md).

---

← Previous: [Persona Guide 09: Client, Patient & Guardian (English)](09-client-patient-and-guardian.md) · [Knowledge Base Home](../README.md) · [Pagsisimula (Taglish Draft)](../GETTING_STARTED_FIL.md) · [FAQ](../FAQ.md) · Next: [Persona Guide 10: Corporate Sponsor & HR Viewer](10-sponsor-and-hr-viewer.md) →
