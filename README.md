# ARA Schema

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

**Agent-maintained wiki page format** — YAML frontmatter, typed relations, citation tags, and confidence markers. Structure only; no domain content.

Part of the [agent toolkit](https://github.com/cemini23/agent-toolkit-demo):

| Tool | Role |
|------|------|
| [vet](https://github.com/cemini23/vet) | Lint skills and briefs before commit |
| [phase0](https://github.com/cemini23/phase0) | Audit third-party repos before adoption |
| [wikilint](https://github.com/cemini23/wikilint) | Enforce graph health on wikis using this schema |
| **ara-schema** | The page contract wikilint expects |

## Quick start

1. Copy `examples/minimal-page.md` into your wiki.
2. Run `wikilint wiki/` in CI ([demo workflow](https://github.com/cemini23/agent-toolkit-demo/blob/main/.github/workflows/agent-toolkit.yml)).
3. Optional: lint briefs with `vet --profile brief`.

Full spec: [SCHEMA.md](./SCHEMA.md)

## Why

LLM-curated wikis rot fast — orphan pages, one-way `related:` links, `@mentions` without files. ARA gives agents a **stable contract**; wikilint enforces it in CI.

## Related

- Methodology newsletter: [Outlier Weekly](https://outlierweekly.substack.com)
- YouTube: [@Cemini23](https://www.youtube.com/@Cemini23)
- Agent meta-wiki: [cemini-claude-code-CCC](https://github.com/cemini23/cemini-claude-code-CCC)
- Toolkit: [vet](https://github.com/cemini23/vet) · [wikilint](https://github.com/cemini23/wikilint) · [phase0](https://github.com/cemini23/phase0) · [agent-toolkit-demo](https://github.com/cemini23/agent-toolkit-demo)

## License

MIT — use the schema in any project; keep your wiki content private.
