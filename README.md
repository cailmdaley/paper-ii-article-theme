# Paper II article theme

This repository contains a scoped build of the ASTRA article theme for the
UNIONS-3500 B-mode validation report.
It does not replace LightconeResearch's shared theme release.

The source is [cailmdaley/astra-theme at `808d959`](https://github.com/cailmdaley/astra-theme/tree/808d95925b25486a91b1820b178222646a818ddf), based on upstream v0.0.16.
`build-provenance.json` records the exact source commit, dependency-lock hash,
build commands, and local validation.
The source's `patches/@astra-spec+ui+0.0.6.patch` preserves excluded-option labels
and reasons in the shared record dialog renderer.

Use the versioned artifact in a MyST project:

```yaml
site:
  template: https://github.com/cailmdaley/paper-ii-article-theme/archive/refs/tags/v0.0.16-paper-ii.2.zip
```

The theme renders authored Markdown and math in record dialogs and previews,
opens resolvable record links inside the existing detail stack, and opens
inherited figure-provenance decisions without leaving the report.
Modified clicks and keyboard events retain native link behavior.
Embedded insight claims resolve relative links in their own declaring scope,
including when they appear in a decision or paper's insight collection.
Links inside those claims keep their own keyboard and mouse activation.
Descriptions and exclusion reasons remain the specification's own text.

When a report already provides a handwritten caption after an ASTRA output,
`:class: astra-output--no-caption` suppresses only the spec-derived article
caption.
The record dialog still displays its description.

The runtime needs Node 20 or later and `npm ci`.
The full source validation uses `npm ci`, `npm test`, `npm run typecheck`, and
`npm run build:article`.
No scientific outputs or analysis specifications are included or changed here.
