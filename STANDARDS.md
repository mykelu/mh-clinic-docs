# Documentation Standards (for every contributor and AI agent)

> **Navigation:** [Knowledge Base Home](README.md) · [Contributing](CONTRIBUTING.md) · [Document Register](DOCUMENT_REGISTER.md) · [Changelog](CHANGELOG.md)
>
> **Doc ID:** `MHD-REF-07` · **Type:** Reference · **Audience:** Contributors, reviewers and AI agents · **Revised:** 25 November 2026 · All examples use synthetic data.

These standards are **binding** for every change to this repository and its [wiki](https://github.com/mykelu/mh-clinic-docs/wiki), whether a person or an AI agent makes it. [CONTRIBUTING.md](CONTRIBUTING.md) is the short how-to; [AGENTS.md](AGENTS.md) is the agent entry point; this page is the full rule set. If they disagree, this page wins.

## 1. What this repository is

`mh-clinic-docs` is the **public showcase knowledge base** for MH-Clinic. It presents the full platform vision (Product Owner decision, 24 November 2026). It is **not** a standard operating procedure (SOP): operational procedures live in the private source-of-record repository. Every page must be safe to publish to anyone.

## 2. Where a page goes (Diataxis)

| The reader wants to… | Type (Doc ID line) | Folder | ID area |
| :--- | :--- | :--- | :--- |
| Learn by doing with synthetic data | Tutorial | `training/` | `TRN` |
| Complete one task | How-to guide | `personas/`, root guides | `PER`, `HOW` |
| Look something up | Reference | `manuals/`, root reference pages | `MAN`, `REF` |
| Understand the platform and why | Explanation | `decks/` | `DCK` |
| Know the rules | Reference | root (`SECURITY.md`) | `POL` |
| Start here | Reference | `README.md` | `HOM` |

Images go in `assets/screenshots/` (PNG) and `assets/visuals/` (SVG). Do not add a new top-level folder without updating this table, [README.md](README.md) and [INDEX.md](INDEX.md).

## 3. File naming

- Ordered sets: `NN-kebab-case.md` (for example `personas/02-front-desk-coordinator.md`). Use the next free number; never renumber published files.
- Root pages: `UPPER_SNAKE_CASE.md` (for example `GETTING_STARTED.md`).
- Images: `kebab-case.png` / `kebab-case.svg`. ASCII only, no spaces.
- Wiki pages: `Title-With-Dashes.md` (see §11).

## 4. Required page header and footer

Every page has, in this order:

1. One `#` H1 title.
2. A navigation line: `> **Navigation:** [Knowledge Base Home](README.md) · …related pages…`
3. The Doc ID line, exactly in this shape:
   `> **Doc ID:** \`MHD-XXX-NN\` · **Type:** Tutorial | How-to guide | Reference | Explanation · **Audience:** … · **Revised:** DD Month YYYY · All examples use synthetic data.`
4. Body headings in order (`##`, then `###`), never skipping a level.
5. A footer: `---`, then `← Previous: […] · [Knowledge Base Home] · [Getting Started] · [FAQ] · Next: […] →`.

Decks also have an **Agenda** before Slide 1 and a **Summary & Next Steps** after the last slide.

## 5. ID scheme

`MHD-<AREA>-<NN>` with areas `DCK` decks, `MAN` manuals, `PER` persona guides, `TRN` training, `REF` reference, `HOW` how-to guides, `POL` policy, `HOM` home, `WIK` wiki pages. Take the next free number from the [Document Register](DOCUMENT_REGISTER.md). Never reuse an ID.

## 6. Register and changelog rule

In the **same pull request** as any change:

1. **New page:** add a row to [DOCUMENT_REGISTER.md](DOCUMENT_REGISTER.md) (ID, title, path, type, revised date).
2. **Changed page:** update its **Revised** date on the page and in the register.
3. **Every pull request:** add a dated bullet to [CHANGELOG.md](CHANGELOG.md) (newest first, dates in PHT).
4. **Retired page:** keep the ID in the register with "Retired — see `MHD-…`"; redirect readers with a one-line page rather than deleting it when links may exist.

## 7. Review status

- Contributors and agents open pull requests; **only the Product Owner (Michael) approves and merges.** An agent never approves, merges, or describes a page as "approved".
- Statements about law or regulation say "confirm with a lawyer or the DPO" until a lawyer or the DPO confirms them.
- Translations (Filipino/Taglish) are marked "needs native-speaker review" until reviewed.

## 8. Truth and showcase rules

- This repository **may describe the complete platform vision** in present tense. That is the agreed showcase register.
- Even so, **never invent**: routes must exist in the application (`/staff/appointments`, `/client/[brand]`…), work package numbers must match the Master PRD (`WP-01`–`WP-32`), role names must match the role model, and numbers (report counts, measure counts) must match the manuals. If a fact cannot be verified, leave it out.
- Do not publish internal security posture, infrastructure hostnames, CI internals, vulnerability details or unmerged-PR status.
- Do not publish emergency hotline numbers until they are verified (see issue [#6](https://github.com/mykelu/mh-clinic-docs/issues/6)); `911` (Philippine national emergency number) is acceptable.
- Mark assumptions and estimates as such.

## 9. Privacy and data

- **Synthetic data only:** `@example.test` addresses, invented names, invented member IDs and record references.
- **Never include:** real patient or client information, real licence or PRC numbers, live HMO member IDs, credentials, tokens, internal hostnames, IP addresses or personal mailboxes.
- Privacy contact: the Data Protection Officer at `dpo@cml-intl.com`. Security reports follow [SECURITY.md](SECURITY.md) and never go into a public issue or pull request.

## 10. Voice, tone and formatting

- Plain, active, second person ("Select **Save**"). One idea per sentence; one task per numbered step; put the check after the step.
- UI labels in **bold**; routes, roles, IDs and code in backticks.
- Dates as "25 November 2026"; times in Philippine Time (PHT).
- Tables have a header row, a separator row and the same number of cells in every row.
- Use the terms in the [Glossary](GLOSSARY.md); add a glossary entry for any new acronym and link it on first use.
- Spell out an acronym on first use per page (for example "Columbia Suicide Severity Rating Scale (`C-SSRS`)").

## 11. Screenshots, images and diagrams

- Capture from a synthetic training tenant only; check every visible field before committing.
- Alt text says what the screen shows and why it matters, never just "screenshot".
- Caption below each image: `*Synthetic <role> capture, <Month YYYY>.*`
- SVGs include `role="img"`, `<title>` and `<desc>`. Follow [ACCESSIBILITY.md](ACCESSIBILITY.md).
- No machine-local paths (`file://`, `/Users/…`); use repository-relative paths.

## 12. Links

- Relative links inside the repository; anchors must match the target heading.
- Wiki pages link to repository files with full URLs: `https://github.com/mykelu/mh-clinic-docs/blob/main/<path>`.
- Never link to private repositories, internal hosts or staging URLs.
- Check links before review (optional local command: `npx markdown-link-check -c .markdown-link-check.json <file>`).

## 13. FAQ and wiki rules

- **FAQ** ([FAQ.md](FAQ.md) and the wiki [FAQ](https://github.com/mykelu/mh-clinic-docs/wiki/FAQ)): write each entry as the question a real user would ask, grouped by role (patient/guardian, front desk, clinician, administrator, case manager, corporate sponsor, helpline). Answer in 1–3 sentences, then link the manual or persona guide. When a page changes behaviour a user would notice, update the matching FAQ answer in the same pull request.
- **Wiki** (repository `mh-clinic-docs.wiki.git`): a friendly front door, not a second copy of the manuals. Every wiki page has the same header shape as §4 (`MHD-WIK-NN` IDs), links to the canonical repository page for detail, and is listed in `_Sidebar.md`. `_Footer.md` carries the synthetic-data and privacy notice. Page filenames use dashes (`Getting-Started.md`); links use `[Text](Page-Name)`.
- When a repository page is added or renamed, update `_Sidebar.md`, the wiki [Changelog](https://github.com/mykelu/mh-clinic-docs/wiki/Changelog) and any wiki link to it.
- Wiki edits are pushed to `mh-clinic-docs.wiki.git` directly (wikis have no pull requests). Record the wiki commit in the repository [CHANGELOG.md](CHANGELOG.md).

## 14. Issues

- Log documentation gaps as GitHub issues in this repository with the `documentation` label, a one-line summary, the affected pages and a suggested fix. Use `decision` when the Product Owner must choose.
- Search existing issues first; add to an open issue rather than duplicating it.
- Never post security vulnerabilities, personal data or internal security posture in an issue.

## 15. Pull request checklist

The checklist is in [`.github/PULL_REQUEST_TEMPLATE.md`](.github/PULL_REQUEST_TEMPLATE.md):

- [ ] Header (H1, Navigation, Doc ID line) and Previous/Next footer present.
- [ ] Register row added or updated; **Revised** dates updated; CHANGELOG bullet added.
- [ ] Routes, `WP-` numbers, role names and counts verified; nothing invented.
- [ ] Synthetic data only; no secrets, personal data, internal hosts or personal mailboxes.
- [ ] One H1; no skipped headings; tables well-formed; glossary terms linked.
- [ ] Images have descriptive alt text and a dated synthetic caption; SVGs have `<title>` and `<desc>`.
- [ ] Links checked; FAQ and wiki updated if user-facing behaviour changed.
- [ ] Legal statements say "confirm with a lawyer or the DPO"; translations marked for review.

Optional local lint: `npx markdownlint-cli2 "**/*.md"` with [`.markdownlint.json`](.markdownlint.json). No automated workflow runs these checks.

---

← Previous: [Contributing and Style Guide](CONTRIBUTING.md) · [Knowledge Base Home](README.md) · [Getting Started](GETTING_STARTED.md) · [FAQ](FAQ.md) · Next: [Document Register](DOCUMENT_REGISTER.md) →
