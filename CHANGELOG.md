# Changelog

> **Navigation:** [Knowledge Base Home](README.md) · [Document Register](DOCUMENT_REGISTER.md)
>
> **Doc ID:** `MHD-REF-06` · **Type:** Reference · **Revised:** 25 November 2026

Dates are in Philippine Time (PHT).

## 25 November 2026: repository license notice and additional RBAC SVG contrast polish

- **Repository license notice (#3, pending Product Owner / legal confirmation):** Added `LICENSE` (`All rights reserved` notice for the public showcase knowledge base) and linked it from [README.md](README.md).
- **Additional SVG contrast polish (#7):** Darkened the remaining 5 muted `#64748B` cells on `#FAFAF8`/`#FFFFFF` rows in [`assets/visuals/role-rbac-isolation-matrix.svg`](assets/visuals/role-rbac-isolation-matrix.svg) to `#475569`, raising its measured minimum contrast from `4.55:1` to `5.24:1` ([ACCESSIBILITY.md](ACCESSIBILITY.md)).

## 25 November 2026: WCAG SVG contrast audit, screenshot provenance, verified crisis hotlines, and Filipino/Taglish drafts

- **WCAG 2.2 AA SVG contrast audit & fix (#7):** Measured all 399 text elements across all 8 SVG diagrams; darkened two muted cells in `assets/visuals/role-rbac-isolation-matrix.svg` (`#64748B` → `#475569` on `#EEF2FF`, `4.26:1` → `6.77:1`) so 100% of SVG text passes `>= 4.55:1`; recorded exact per-diagram contrast ratios and 59-PNG zoom/resolution findings in [ACCESSIBILITY.md](ACCESSIBILITY.md).
- **Screenshot capture provenance & refresh checklist (#8):** Recorded the 24 November 2026 synthetic capture date, application baseline, and pending re-captures in [VISUAL_GUIDE.md](VISUAL_GUIDE.md), and added a release screenshot-refresh rule to [CONTRIBUTING.md](CONTRIBUTING.md).
- **Verified Philippine National Crisis Hotlines (#6):** Verified `911`, `NCMH 1553`, `In Touch`, and `Hopeline PH` against official DOH, DILG, eHotlines, In Touch, and DSWD pages on 25 November 2026 (PHT) and added a source-cited reference table (pending clinical reviewer confirmation) in [Manual 07](manuals/07-helpline-learning-hub-and-ai-coordinator.md), linked from the [Executive Deck](decks/01-executive-introduction-deck.md) and [Glossary](GLOSSARY.md).
- **Draft Filipino/Taglish editions (#10):** Added [Pagsisimula (`GETTING_STARTED_FIL.md`)](GETTING_STARTED_FIL.md) (`MHD-HOW-04`) and [Gabay ng Persona 09 (`personas/09-client-patient-and-guardian-fil.md`)](personas/09-client-patient-and-guardian-fil.md) (`MHD-PER-11`), marked **needs native-speaker review**, and linked both from [README.md](README.md), [FAQ.md](FAQ.md), and [DOCUMENT_REGISTER.md](DOCUMENT_REGISTER.md).

## 25 November 2026: helpline visual guidance

- Labelled the existing passcode screenshot as a feature-enabled view. The client guide, visual index, Manual 07 and Lab 09 now distinguish it from the unavailable view without treating it as a started session.

## 25 November 2026: standards, wiki and consistency sweep

- Added [Documentation Standards](STANDARDS.md) (`MHD-REF-07`), binding for people and AI agents, plus agent entry points (`AGENTS.md`, `CLAUDE.md`, `.cursor/rules/docs.mdc`, `.github/copilot-instructions.md`), a pull request template with a documentation checklist, and optional local lint and link-check configurations.
- Reconciled `WP-` numbers in the persona guides, training labs, onboarding checklist and manuals with the Master PRD numbering (`WP-01`–`WP-32`); removed codes that had no matching work package.
- Removed duplicate route rows in Persona Guides 02, 05, 06 and 08.
- Aligned Persona Guide 06 and Lab 06 with the Certified Medical Acupuncturist (`CMA`) role and its acupuncture screens.
- Added Previous / Next footers to every root page.
- Corrected the helpline acuity order in Persona Guide 07 to match the platform (`L1` is imminent life safety, `L4` is informational).
- Published the [project wiki](https://github.com/mykelu/mh-clinic-docs/wiki) (19 pages plus sidebar and footer; wiki commit `8165b05`): home page, getting started, one page per role, a role-based FAQ and troubleshooting page, glossary, features overview, training index, security and privacy contacts, and a changelog.

## 25 November 2026: navigation, accessibility and onboarding

- Added [Getting Started](GETTING_STARTED.md) with reading paths by role and time available.
- Added a [FAQ](FAQ.md), a [Contributing and Style Guide](CONTRIBUTING.md), an [Accessibility Statement](ACCESSIBILITY.md) and a [Document Register](DOCUMENT_REGISTER.md).
- Added a Doc ID line (ID, Diataxis type, audience, revision date) to every page.
- Added Previous / Next footer navigation across decks, manuals, persona guides and training.
- Added Agenda and Summary & Next Steps sections to all three decks.
- Added `<title>` and `<desc>` to all eight SVG diagrams.
- Corrected the glossary definition of `CMA` (Certified Medical Acupuncturist).

## 24–25 November 2026: route and consistency pass

- Aligned screen paths with the application, added the glossary and `SECURITY.md`, and described the gated helpline flow in Lab 09 and Persona 09.
- Added the Data Protection Officer contact.

## 24 November 2026: initial publication

- Published the manuals, persona guides, training labs, decks, synthetic screenshots and architecture diagrams.

---

← Previous: [Document Register](DOCUMENT_REGISTER.md) · [Knowledge Base Home](README.md) · [Getting Started](GETTING_STARTED.md) · [FAQ](FAQ.md)
