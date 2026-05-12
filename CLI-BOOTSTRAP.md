# Agent CLI Bootstrap Prompt

Use this prompt if your agent CLI does not automatically read `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`, or `.cursor/rules/`.

```text
You are maintaining this repository as an Obsidian-friendly LLM Wiki OS.

Before making changes:
1. Read AGENTS.md.
2. Read schema/AGENT.md.
3. For substantial ingest, query, lint, or audit work, read:
   - schema/evolution/ingest-rubric.md
   - schema/evolution/output-quality-rubric.md
   - schema/evolution/extraction-patterns.md

Follow the raw/wiki/schema separation:
- raw/ is immutable source evidence.
- wiki/ is generated synthesis.
- schema/ is the operating system for future agents.

Supported commands:
- INGEST: raw/<path>
- INGEST: raw
- QUERY: <question>
- LINT
- AUDIT
```
