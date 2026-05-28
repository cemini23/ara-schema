# ARA wiki page schema

Version 0.1 — structure spec for agent-maintained markdown wikis.

## Frontmatter (required)

```yaml
---
title: Human-readable page title
type: source | entity | concept | brief
tags: [coarse, labels]
keywords: [search, terms]
related:
  - path/to/related-page.md
maturity: draft | validated | core
created: YYYY-MM-DD
updated: YYYY-MM-DD
---
```

- `type` selects which body sections apply.
- `related[]` must be **bidirectional**: if A lists B, B must list A.
- `maturity`: `draft` → `validated` → `core` as evidence accumulates.

## Body sections (in order)

| Section | When |
|---------|------|
| `## Relations` | Always — inline `@path/to/page.md` matching `related:` |
| `## Raw Concept` | Provenance (source metadata or synthesis prompt) |
| `## Narrative` | Main content |
| `## Snippets` | Verbatim quotes with citations |
| `## Dead Ends` | Optional — failed approaches and lessons |

## Cross-links

- Inline: `@path/to/page.md` (relative to wiki root, no leading slash)
- Typed edges (optional): `@I path` import, `@B path` bound, `@M path` baseline

## Citations

- Source file: `[Source: filename.pdf p.5]`
- URL: `[Source: https://example.com (retrieved YYYY-MM-DD)]`

## Claim confidence

| Tag | Meaning |
|-----|---------|
| `[CONFIRMED]` | ≥2 independent sources |
| `[TENTATIVE]` | Single source |
| `[NEEDS VERIFICATION YYYY-MM-DD]` | Plausible, untested — include date for staleness lint |
| `[RETRACTED]` | Disproven; keep with note |

## Directory layout (convention)

```
wiki/
  index.md          # catalog
  log.md            # append-only ops log
  sources/          # one page per ingested source
  entities/         # tickers, people, tools, …
  concepts/         # topics and methodologies
```

Nested paths under `entities/` are allowed when hierarchy helps.

## CI integration

```yaml
- uses: cemini23/wikilint@v0.1.0
  with:
    wiki-dir: wiki
    strict: "false"
```

See [wikilint](https://github.com/cemini23/wikilint) for check categories.
