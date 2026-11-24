# AGENTS.md — instructions for AI agents

This is the **public showcase** knowledge base for MH-Clinic. Any agent (Cursor, Claude, Copilot, Codex, Grok Bot or other) that changes this repository or its wiki must follow [STANDARDS.md](STANDARDS.md) (`MHD-REF-07`).

**Must do**
- Use the page header (H1, Navigation line, Doc ID line) and Previous/Next footer from STANDARDS.md §4.
- Add or update the [Document Register](DOCUMENT_REGISTER.md) row and a [CHANGELOG.md](CHANGELOG.md) bullet in the same pull request.
- Verify routes against the application, `WP-` numbers against the Master PRD (`WP-01`–`WP-32`), and terms against the [Glossary](GLOSSARY.md). Never invent facts.
- Use synthetic data only (`@example.test`). Privacy contact: `dpo@cml-intl.com`.
- Complete the checklist in [`.github/PULL_REQUEST_TEMPLATE.md`](.github/PULL_REQUEST_TEMPLATE.md).

**Must not**
- Approve or merge pull requests, or call anything "approved" — only the Product Owner (Michael) approves.
- Publish secrets, personal data, real patient data, internal hostnames, CI internals, security posture or unverified hotline numbers.
- Add GitHub Actions workflows or change repository settings.

The private source of record (SOPs, truthful status) is a separate repository; do not copy internal-only content here.
