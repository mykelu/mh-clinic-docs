# Accessibility Statement and Checklist

> **Navigation:** [Knowledge Base Home](README.md) · [Contributing](CONTRIBUTING.md)
>
> **Doc ID:** `MHD-REF-04` · **Type:** Reference · **Audience:** Readers and contributors · **Revised:** 25 November 2026

We aim for this knowledge base to be usable with screen readers, keyboard navigation and zoom. The aim is aligned with WCAG 2.2 AA. It has not been independently audited.

## What is in place (checked 25 November 2026)

- All 129 Markdown image references have descriptive alt text (an automated check found none empty or shorter than 8 characters).
- All 8 SVG diagrams (`assets/visuals/*.svg`, 399 text elements) declare `role="img"` and include `<title>` and `<desc>` elements.
- **Measured SVG colour contrast (25 November 2026 PHT):** Automated WCAG 2.2 AA contrast measurement across all 8 SVGs confirmed **0 failures** after darkening two muted `#64748B` cells on `#EEF2FF` in `role-rbac-isolation-matrix.svg` to `#475569` (`4.26:1` → `6.77:1`). Measured minimum text contrast across every diagram is `>= 4.64:1` (normal text threshold `4.5:1`, large text `3.0:1`):
  - `bi-30-reports-map.svg` (49 text elements): minimum `4.76:1`
  - `clinical-safety-and-coding.svg` (48 text elements): minimum `4.86:1`
  - `eight-gate-booking-flow.svg` (57 text elements, incl. `#FFFFFF` on `#1F5C48` badges at `7.83:1`): minimum `4.64:1`
  - `helpline-ai-guardrails.svg` (36 text elements): minimum `5.62:1`
  - `platform-architecture-overview.svg` (61 text elements): minimum `4.86:1`
  - `role-rbac-isolation-matrix.svg` (51 text elements): minimum `4.83:1` (after fix)
  - `six-layer-policy-hierarchy.svg` (56 text elements): minimum `4.76:1`
  - `three-operating-modes.svg` (41 text elements): minimum `5.02:1`
- **Screenshot zoom & resolution check (59 PNGs, 25 November 2026 PHT):** 51 full-page and panel captures are `886px`–`1920px` wide (readable at 200% zoom). 8 compact UI-element crops are narrower than `800px` (`accounting-review-journal-approval.png`, `appointment-details-panel.png`, `assessment-client-submitted.png`, `assessment-client-task.png`, `assessment-coordinator-assigned.png`, `client-unpublished-hours.png`, `soap-draft-conflict.png`, `soap-first-draft-version.png`); each is paired with descriptive alt text, a caption, and surrounding step prose repeating every label and action.
- Every page has a single H1, and a scan found no skipped heading levels.
- Every page has navigation links at the top and bottom, so readers don't need to scroll back.
- Tables use header rows, and link text names its destination.
- Draft Filipino/Taglish editions of [Getting Started (`GETTING_STARTED_FIL.md`)](GETTING_STARTED_FIL.md) and [Client, Patient & Guardian Guide (`personas/09-client-patient-and-guardian-fil.md`)](personas/09-client-patient-and-guardian-fil.md) are available (marked **needs native-speaker review**).

## Known limitations

- Screenshots contain text as raster images; pixel-level contrast inside third-party browser captures has not been separately audited, and small UI labels in compact crops rely on the accompanying captions and step prose.
- Mermaid diagrams depend on GitHub's renderer. The surrounding text describes the flow.
- Filipino/Taglish translations are currently drafts awaiting native-speaker review before publication.

## Contributor checklist

- [ ] Alt text says what the image shows and why it matters, not "screenshot".
- [ ] Headings go H1 → H2 → H3 without skipping levels.
- [ ] Link text makes sense out of context.
- [ ] No information is conveyed by colour alone.
- [ ] Tables have a header row.
- [ ] New SVGs include `role="img"`, `<title>`, `<desc>`, and pass WCAG 2.2 AA contrast (`>= 4.5:1` normal text, `>= 3.0:1` large text).

---

← Previous: [Visual Guide](VISUAL_GUIDE.md) · [Knowledge Base Home](README.md) · [Getting Started](GETTING_STARTED.md) · [FAQ](FAQ.md) · Next: [Security](SECURITY.md) →
