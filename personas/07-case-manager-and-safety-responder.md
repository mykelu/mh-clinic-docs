# Persona Guide 07: Case Manager & Safety Responder

> **Navigation:** [Knowledge Base Home](../README.md) · [Master Index](../INDEX.md) · [ABC Bank IHC & Case Management](../manuals/05-abc-bank-ihc-and-case-management.md) · [Helpline & AI Coordinator](../manuals/07-helpline-learning-hub-and-ai-coordinator.md) · [Role Exercises & Labs](../training/01-role-exercises-and-labs.md)

---

## 1. Role Summary & Scope

The **Case Manager & Safety Responder** (`CASE_MANAGER` / `SAFETY_RESPONDER`) oversees high-acuity care coordination, post-discharge/no-show outreach, `C-SSRS` safety plan follow-ups, `MDT` referrals, and **Anonymous Helpline (`WP-31`) crisis escalation (`L3`–`L4`)**.

| Dimension | Details |
| :--- | :--- |
| **Primary Workspaces** | `/cases`, `/cases/safety`, `/helpline/console`, `/ihc/mdt`, `/schedule/waitlist` |
| **Core Work Packages** | `WP-09` C-SSRS & Safety Plans, `WP-18` Case Management & Outreach, `WP-26` MDT Hub, `WP-31` Anonymous Helpline |
| **SLA Targets** | `L4` Crisis Escalation: immediate acknowledgment; `High` C-SSRS No-Show: outreach within 2 hours |
| **Data Visibility** | Safety flags, care plans, outreach logs, and `ANON-xxxx` helpline sessions (pseudonymous until explicit consent-to-identify) |

---

## 2. Core Workflows

### 2.1 High-Risk Safety Queue (`/cases/safety`)
1. Monitor active alerts triggered by:
   - **`C-SSRS` Moderate/High** scores (`WP-09`)
   - **Missed appointments** for flagged high-risk clients
   - **Helpline `L3` / `L4` escalations** (`WP-31`)
2. Open the client's **6-Step Safety Plan** and confirm emergency contact / guardian notification rules.
3. Log every outreach attempt (`PHONE`, `SMS`, `PORTAL`, `EMERGENCY_DISPATCH`) with timestamp and outcome.

### 2.2 Anonymous Helpline Responder Console (`WP-31`)

```mermaid
flowchart LR
    A["Caller Connects<br/>(ANON-xxxx)"] --> B["Triage Level<br/>L1 / L2 / L3 / L4"]
    B -->|L1-L2| C["Supportive Listening &<br/>/learn Self-Help Links"]
    B -->|L3| D["Warm Referral to<br/>Intake / Clinic Slot"]
    B -->|L4 Imminent Risk| E["National Hotline Deflection<br/>& Crisis Protocol"]
    C --> F["15-Min Cooldown<br/>& Structured Wrap-Up"]
```

1. Accept incoming anonymous sessions tagged with ephemeral `ANON-xxxx` IDs (zero PII stored by default).
2. Classify acuity **`L1` (Low)** through **`L4` (Imminent Crisis)**.
3. For **`L4`**, follow the **National Hotline Deflection** and emergency response protocol immediately.
4. Only convert `ANON-xxxx` to a clinic intake record if the caller **explicitly opts in** to warm referral.
5. Respect the mandatory **15-minute post-crisis cooldown** between high-acuity responder sessions to prevent responder burnout.

### 2.3 Multidisciplinary Team (`MDT`) Coordination (`/ihc/mdt`)
- Coordinate warm handoffs across `MD` (Psychiatry/Neurology), `RPsy` (Psychotherapy), `IHC` (Counseling), and `RND` (Nutrition).
- Track referral acceptance, shared goals, and barrier resolution (transport, HMO LOA delays, medication adherence).

---

## 3. Visual Workspace Reference

![WP-31 Zero-PII Anonymous Helpline and WP-32 AG-UI AI Coordinator Safety Guardrails](../assets/visuals/helpline-ai-guardrails.svg)

![Case episodes workspace scoped to MindWell.PH showing follow-up queue in Philippine time and New case episode action](../assets/screenshots/case-manager-episodes.png)

*Synthetic case-manager training capture, November 2026. Case episodes track longitudinal follow-up windows strictly within the authorized brand.*

![L1–L4 Crisis Helpline Responder Desk listing brand-scoped endpoints and 15-minute post-L1 cooldown reminder](../assets/screenshots/staff-helpline-desk.png)

*Synthetic responder-training capture, November 2026. Responder consoles keep caller aliases pseudonymous (`ANON-xxxx`) and enforce post-`L1` welfare cooldowns.*

![Entitlement-Gated Anonymous Helpline showing Immediate Public Crisis Support deflection numbers](../assets/screenshots/helpline-public-deflection.png)

*Synthetic public-access training capture, November 2026. Unentitled visitors immediately receive Philippine National Crisis Hotline deflection numbers.*

---

## 4. Practice & Verification
- Complete **Lab 07** in [Role Exercises & Labs](../training/01-role-exercises-and-labs.md).
- Review full helpline & safety details in [Manual 07: Helpline, Learning Hub & AI Coordinator](../manuals/07-helpline-learning-hub-and-ai-coordinator.md).
