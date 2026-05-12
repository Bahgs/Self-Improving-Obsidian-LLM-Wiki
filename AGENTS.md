---
title: LLM Wiki Agent Instructions
tags:
  - llm-wiki
  - agents
created: 2026-05-12
updated: 2026-05-12
---

# LLM Wiki Agent Instructions

This vault is an Obsidian-friendly LLM Wiki. Before making durable wiki changes, read `schema/AGENT.md` and follow its raw/wiki/schema separation rules.

The operating principle is:

- `raw/` is immutable evidence.
- `wiki/` is generated synthesis.
- `schema/` is the evolving operating system.

Use the visible skill documentation in `Skills/` when the task matches a skill:

- `Skills/obsidian-markdown/SKILL.md` for Obsidian markdown, wikilinks, embeds, callouts, and frontmatter.
- `Skills/obsidian-bases/SKILL.md` for `.base` files, table/card/list/map views, formulas, filters, and Base validation.
- `Skills/obsidian-cli/SKILL.md` when interacting with a running Obsidian instance or verifying plugin/theme behavior through the Obsidian CLI.
- `Skills/json-canvas/SKILL.md` for `.canvas` files, visual canvases, and JSON Canvas graph work.
- `Skills/defuddle/SKILL.md` for extracting clean markdown from web pages before ingesting or analyzing web sources.

The hidden `.agents/skills/` directory may also exist as an agent-runtime install location. Treat `Skills/` as the human-visible copy inside the vault and `.agents/skills/` as compatibility infrastructure.

## Required Workflow

For `INGEST`, `QUERY`, `LINT`, or `AUDIT`, read `schema/AGENT.md` first.

For substantial source ingests, also read:

- `schema/evolution/ingest-rubric.md`
- `schema/evolution/output-quality-rubric.md`
- `schema/evolution/extraction-patterns.md`

Never modify files under `raw/` unless the user explicitly asks for source-archive setup or organization.
