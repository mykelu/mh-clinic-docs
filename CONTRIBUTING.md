# Contributing and Style Guide

> **Navigation:** [Knowledge Base Home](README.md) · [Accessibility](ACCESSIBILITY.md) · [Document Register](DOCUMENT_REGISTER.md)
>
> **Doc ID:** `MHD-HOW-03` · **Type:** How-to guide · **Audience:** Documentation contributors · **Revised:** 25 November 2026

The full, binding rule set for people and AI agents is [STANDARDS.md](STANDARDS.md); agents start at [AGENTS.md](AGENTS.md).

## Non-negotiable rules

1. **Synthetic data only.** Use `@example.test` addresses, invented names and invented identifiers. Never include real patient information, real licence numbers, live HMO member IDs, credentials, internal hostnames or personal mailboxes.
2. **Routes must match the application.** Write route paths exactly as the app uses them, for example `/staff/appointments` or `/client/[brand]`.
3. **Security issues go to [SECURITY.md](SECURITY.md)**, never into a public issue or pull request.

## Page structure

Every page has, in this order:

1. One `#` H1 title.
2. A `> **Navigation:**` line linking home and related pages.
3. A `> **Doc ID:**` line: ID from the [Document Register](DOCUMENT_REGISTER.md), type (Explanation / Reference / How-to guide / Tutorial), audience, revised date, and the synthetic-data note.
4. Body headings in order (`##`, then `###`), without skipping levels.
5. A footer `---` followed by Previous / Home / Getting Started / FAQ / Next links.

Decks also have an **Agenda** section before Slide 1 and a **Summary & Next Steps** section after the last slide.

## Writing style

- Use plain, active language and the second person ("Select **Save**").
- Use one idea per sentence and one task per numbered step.
- Put the result or check after the step: "Check that the status shows **Confirmed**."
- Put code, routes, roles and identifiers in backticks.
- Write dates as "25 November 2026" and times in Philippine Time (PHT).

## Screenshots and diagrams

- Capture from a synthetic training tenant only, and check every visible field before committing.
- Save screenshots under `assets/screenshots/` as `kebab-case.png`, and diagrams under `assets/visuals/` as SVG.
- Every image needs descriptive alt text (what the screen shows and why it matters), plus an italic caption that starts with "Synthetic … capture, Month YYYY."
- SVGs must include `role="img"`, a `<title>` and a `<desc>`.
- Follow [ACCESSIBILITY.md](ACCESSIBILITY.md).

## Changes

1. Branch from `main` and open a pull request.
2. Update the [Document Register](DOCUMENT_REGISTER.md) and [CHANGELOG.md](CHANGELOG.md).
3. Check links and alt text before you request review.

---

← Previous: [Security](SECURITY.md) · [Knowledge Base Home](README.md) · [Getting Started](GETTING_STARTED.md) · [FAQ](FAQ.md) · Next: [Documentation Standards](STANDARDS.md) →
