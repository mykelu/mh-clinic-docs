# MH-Clinic Visual Guide

Use this guide to find a screenshot at the point where you need to choose an action or confirm its result. Each link opens the illustrated step in its manual, with a short explanation of what to look for. The screenshots are from synthetic training exercises and do not verify current deployment or release readiness.

## Sign in, find access, and schedule

| Task | What to look for |
| :--- | :--- |
| [Choose a staff sign-in method](manuals/01-getting-started-and-mfa.md#staff-sign-in-screen) | The Google, passkey, and email/password choices. |
| [Troubleshoot missing connected access](manuals/01-getting-started-and-mfa.md#when-no-connected-workspaces-appear) | The empty workspace state; ask an administrator to check your role and destination access. |
| [Check why staff booking is unavailable](manuals/02-scheduling-and-hmo-operations.md#when-the-booking-panel-shows-no-published-hours) | The no-published-hours message and disabled booking action. |
| [Retry an HMO availability lookup](manuals/02-scheduling-and-hmo-operations.md#when-an-hmo-availability-lookup-fails) | The refresh control after a failed lookup; wait for the result before proceeding. |

## Document a visit or track an assessment

| Task | What to look for |
| :--- | :--- |
| [Review a note draft conflict](manuals/03-clinical-workflows-and-prescribing.md#reviewing-a-note-draft-conflict) | The conflict notice and disabled save control; compare against the current saved version. |
| [Check a saved certificate draft](manuals/03-clinical-workflows-and-prescribing.md#checking-a-saved-certificate-draft) | The Draft status and revision, not a signed or issued certificate. |
| [Follow an assessment handoff](manuals/04-assessments-and-specialty-tracks.md#following-an-assessment-from-assignment-to-submission) | The coordinator’s assigned status and the linked client’s submission receipt. Neither is report release. |

## Review reports, finance, and outreach

| Task | What to look for |
| :--- | :--- |
| [Check the internal Report Explorer](manuals/06-reporting-and-analytics-guide.md#4-example-internal-report-explorer) | The brand, filters, and timestamp before using an export. |
| [Validate opening rows](manuals/08-accounting-invoicing-and-payouts.md#validate-opening-rows-before-saving) | Accepted rows and balanced totals before a draft is saved. |
| [Review a journal approval](manuals/08-accounting-invoicing-and-payouts.md#review-a-journal-before-approval) | The selected book, date, amount and reason before approving. |
| [Check a closed CRM follow-up](manuals/09-crm-inquiries-and-outreach.md#confirm-a-connected-crm-follow-up-is-closed) | The contact outcome and closed task status; open Clinic separately to check the appointment. |

## Set up a brand and professional access

| Task | What to look for |
| :--- | :--- |
| [Review a brand profile](manuals/10-saas-clients-and-tenant-onboarding.md#review-a-brand-profile-before-saving) | The intended public fields and the required reason before saving. |
| [Prepare a professional invitation](manuals/10-saas-clients-and-tenant-onboarding.md#prepare-professional-access-separately) | The separate staff account, professional access and clinical readiness checks. |

Practice these workflows in the [role-based labs](training/01-role-exercises-and-labs.md) using synthetic data only.

## Screenshot coverage still to add

| Guide | Next useful capture |
| :--- | :--- |
| [ADB in-house counseling and case management](manuals/05-adb-ihc-and-case-management.md) | A no-charge confirmation without record identifiers, then reviewed roster/calendar or shared-plan states. |
| [Helpline, learning hub, and AI coordinator](manuals/07-helpline-learning-hub-and-ai-coordinator.md) | Empty or synthetic triage and handoff states, a reviewed learning item, and a draft-only coordinator action. No caller transcripts or identifying records. |
| [Specialty tracks and formal evaluation](manuals/04-assessments-and-specialty-tracks.md) | Synthetic specialty review and an evaluation release check after both signatures and feedback. |
| [Reporting and analytics](manuals/06-reporting-and-analytics-guide.md) | A scoped Report Studio preview and a separate sponsor report showing suppression of synthetic small cohorts. |
| [Configuration and policy reference](manuals/11-configurations-and-reference.md) | A policy review showing effective scope, inherited value, and revision without internal record identifiers. |
