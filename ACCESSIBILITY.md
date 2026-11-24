# Accessibility Statement and Checklist

> **Navigation:** [Knowledge Base Home](README.md) · [Contributing](CONTRIBUTING.md)
>
> **Doc ID:** `MHD-REF-04` · **Type:** Reference · **Audience:** Readers and contributors · **Revised:** 25 November 2026

We aim for this knowledge base to be usable with screen readers, keyboard navigation and zoom. The aim is aligned with WCAG 2.2 AA. It has not been independently audited.

## What is in place (checked 25 November 2026)

- All 129 Markdown image references have descriptive alt text (an automated check found none empty or shorter than 8 characters).
- All 8 SVG diagrams declare `role="img"` and include `<title>` and `<desc>` elements.
- Every page has a single H1, and a scan found no skipped heading levels.
- Every page has navigation links at the top and bottom, so readers don't need to scroll back.
- Tables use header rows, and link text names its destination.

## Known limitations

- Screenshots contain text as images. The captions and surrounding steps repeat the key information, but small UI labels may not be readable at every zoom level.
- Colour contrast inside screenshots and SVG diagrams has not been measured with a contrast tool.
- Mermaid diagrams depend on GitHub's renderer. The surrounding text describes the flow.
- No Filipino or Taglish edition is available yet.

## Contributor checklist

- [ ] Alt text says what the image shows and why it matters, not "screenshot".
- [ ] Headings go H1 → H2 → H3 without skipping levels.
- [ ] Link text makes sense out of context.
- [ ] No information is conveyed by colour alone.
- [ ] Tables have a header row.
- [ ] New SVGs include `role="img"`, `<title>` and `<desc>`.

---

← Previous: [Visual Guide](VISUAL_GUIDE.md) · [Knowledge Base Home](README.md) · [Getting Started](GETTING_STARTED.md) · [FAQ](FAQ.md) · Next: [Security](SECURITY.md) →
