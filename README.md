# LLM Wiki OS

An Obsidian-first, agent-maintained LLM Wiki framework that turns raw source material into linked notes, concepts, summaries, analysis, and evolving schema rules.

This repo is a sanitized public template. It contains the framework, folder structure, agent instructions, schema, rubrics, and example skill docs. It intentionally contains no private raw files, generated personal notes, credentials, medical records, financial records, chat exports, or personal memory data.

## Why This Exists

The starting point is the LLM Wiki idea popularized by Andrej Karpathy: keep source material and generated knowledge in a persistent text system that an LLM can read, edit, and connect over time.

This framework keeps that foundation but adds a second idea:

> The wiki should not only grow in content. It should also improve the way future agents ingest, summarize, connect, and reason.

Most AI note systems get bigger. This one is designed to get more operationally intelligent. New sources can create new wiki pages, but they can also create schema proposals, output-quality lessons, extraction patterns, and future-agent prompts.

## Quick Start

```bash
git clone <your-repo-url> llm-wiki-os
cd llm-wiki-os
```

Then:

1. Open the folder as an Obsidian vault.
2. Put one non-sensitive source in `raw/web/`, `raw/papers/`, or `raw/Clippings/`.
3. Open your preferred agent CLI in the repo root.
4. Ask it to read `AGENTS.md` and `schema/AGENT.md`.
5. Run your first ingest:

```text
INGEST: raw/path-to-your-source.md
```

After the ingest, review:

- `wiki/sources/`
- `wiki/concepts/`
- `wiki/entities/`
- `wiki/index.md`
- `wiki/log.md`

## Installation

### 1. Use This Template

On GitHub, you can either:

- click **Use this template**, then clone your new repo
- fork it
- clone it directly and rename the remote later

Local setup:

```bash
git clone <repo-url> llm-wiki-os
cd llm-wiki-os
```

### 2. Open in Obsidian

In Obsidian:

1. Choose **Open folder as vault**.
2. Select the `llm-wiki-os` folder.
3. Confirm that these folders are visible:
   - `raw/`
   - `wiki/`
   - `schema/`
   - `Skills/`

This repo includes minimal Obsidian defaults. Local workspace state is ignored so your personal layout is not committed.

### 3. Connect an Agent CLI

This framework does not require a specific AI coding tool. It works with any agent CLI that can read and edit local files.

Included compatibility files:

- `AGENTS.md` for general agent instructions
- `CLAUDE.md` for Claude-style workflows
- `GEMINI.md` for Gemini-style workflows
- `.cursor/rules/llm-wiki-os.mdc` for Cursor-style project rules
- `CLI-BOOTSTRAP.md` for any tool that does not auto-read project instruction files

The canonical operating contract is:

```text
schema/AGENT.md
```

All CLI-specific files point back to that schema. The framework is intentionally not tied to any one CLI, editor, model provider, or vendor.

### 4. Start Your CLI From the Repo Root

Use whichever CLI you prefer, but start it from the repository root:

```bash
cd path/to/llm-wiki-os
```

Then use this bootstrap prompt if your tool does not automatically load project instructions:

```text
Read AGENTS.md and schema/AGENT.md before making changes.
For substantial ingest, query, lint, or audit work, also read:
- schema/evolution/ingest-rubric.md
- schema/evolution/output-quality-rubric.md
- schema/evolution/extraction-patterns.md

Follow the raw/wiki/schema separation:
- raw/ is immutable source evidence.
- wiki/ is generated synthesis.
- schema/ is the operating system for future agents.
```

### 5. Add Sources

Put sources under `raw/`:

```text
raw/web/          cleaned web pages
raw/papers/       PDFs and papers
raw/Clippings/    browser clipper markdown
raw/ideas/        sketches and project ideas
raw/books/        book notes or excerpts you can store
raw/assets/       images or supporting files
```

For a public repo, do not commit private source material. Keep private raw files in a local branch, a private fork, or a separate private vault.

## Agent CLI Setup

### Generic Agent CLI

Start from the repo root and ask the agent:

```text
Read AGENTS.md and schema/AGENT.md. Then wait for my command.
```

Use commands like:

```text
INGEST: raw/web/example.md
QUERY: What are the strongest concepts in the vault?
LINT
AUDIT
```

### AGENTS.md-Compatible CLI

This repo includes `AGENTS.md` as the general project instruction file. If your CLI supports project-level instruction discovery, start it from the repo root so it can read the vault rules before making changes.

Recommended first prompt:

```text
Read AGENTS.md and schema/AGENT.md, then run LINT.
```

### Claude-Style CLI

This repo includes `CLAUDE.md`, which points back to the same neutral operating schema.

Recommended first prompt:

```text
Read CLAUDE.md and schema/AGENT.md. Confirm the ingest workflow.
```

### Gemini-Style CLI

This repo includes `GEMINI.md`, which points back to the same neutral operating schema.

Recommended first prompt:

```text
Read GEMINI.md and schema/AGENT.md. Confirm the ingest workflow.
```

### Cursor-Style Setup

This repo includes:

```text
.cursor/rules/llm-wiki-os.mdc
```

If your editor does not load the rule automatically, paste the prompt from `CLI-BOOTSTRAP.md` into your chat.

## Core Philosophy

The vault has three durable layers:

```text
raw/      immutable source archive
wiki/     generated and interlinked knowledge
schema/   operating rules for future agents
```

The important rule is separation:

- `raw/` is evidence. Do not edit it during ingest.
- `wiki/` is synthesis. It contains source notes, concepts, entities, summaries, and analysis.
- `schema/` is behavior. It tells future agents how to maintain and improve the system.

The fourth practical layer is schema evolution:

```text
schema/evolution/
  ingest-rubric.md
  output-quality-rubric.md
  extraction-patterns.md
  personal-thinking-model.md
  schema-change-log.md
  schema-proposals/
  examples/
```

This is the controlled learning loop. It lets the vault collect lessons without constantly destabilizing the main schema.

## What Makes This Different

Traditional LLM wiki:

```text
raw source -> wiki note -> links
```

This framework:

```text
raw source
  -> source note
  -> concepts/entities/summaries
  -> pull-forward questions
  -> output-quality feedback
  -> extraction-pattern updates
  -> schema proposals
  -> future agents behave better
```

The system is not model training. It does not change neural weights. It improves by accumulating written context that future agents are required to read.

That makes the vault self-improving in a practical way:

- better source-type extraction over time
- fewer duplicate concepts
- stronger distinction between evidence and interpretation
- richer graph connections
- reusable examples of good and bad outputs
- schema proposals that can be tested before promotion
- follow-up prompts for future agents, not just passive summaries

## Folder Structure

```text
.
  AGENTS.md
  README.md
  raw/
    Clippings/
    ideas/
      sketches/
    web/
    papers/
    books/
    assets/
  wiki/
    index.md
    log.md
    entities/
    concepts/
    sources/
    summaries/
    analysis/
  schema/
    AGENT.md
    evolution/
      ingest-rubric.md
      output-quality-rubric.md
      extraction-patterns.md
      personal-thinking-model.md
      schema-change-log.md
      schema-proposals/
      examples/
  Skills/
    README.md
    obsidian-markdown/
    obsidian-bases/
    obsidian-cli/
    json-canvas/
    defuddle/
  Bases/
  Canvases/
  .agents/
    skills/
```

## Core Commands

Agents should treat these user commands as operating modes:

```text
INGEST: raw/<path>
INGEST: raw
QUERY: <question>
LINT
AUDIT
```

### INGEST

Use when adding source material from `raw/` into the wiki.

An ingest should:

- confirm the raw source exists
- leave `raw/` unchanged
- create or update a source note in `wiki/sources/`
- create or update relevant concepts in `wiki/concepts/`
- create or update relevant entities in `wiki/entities/`
- update `wiki/index.md`
- append to `wiki/log.md`
- run a schema-learning pass when the source is substantial

### QUERY

Use when answering questions from the wiki.

A query should:

- start from `wiki/index.md`
- read relevant wiki pages
- follow important wikilinks
- answer from the wiki first
- create a reusable `wiki/analysis/` page when the answer is durable

### LINT

Use for structural health checks:

- broken wikilinks
- orphan notes
- stale index entries
- duplicate concepts
- underlinked source notes
- contradictions or superseded claims

### AUDIT

Use for quality checks:

- what outputs were good
- what outputs were weak
- what schema rules need iteration
- which pull-forward questions should be answered, promoted, sourced, left open, or discarded

## Pull-Forward Questions

Pull-forward questions are a core part of the framework.

They are not automatically homework for the user. They are usually latent prompts for future agents.

Use audience labels:

```markdown
## Pull-Forward Questions

### For Future Agents

- What should a future agent investigate, compare, or synthesize from this source?

### For Schema

- What operating rule might this source improve?

### For User

- What question requires the user's judgment, taste, or lived context?
```

Pull-forward questions should not accumulate forever. During audits and lint checks, mark them mentally or explicitly as:

- `answered`
- `promoted`
- `source-needed`
- `still-open`
- `discarded`

## Implementation Guide

1. Open this folder as an Obsidian vault.
2. Put source files into `raw/`.
3. Start your preferred agent CLI from the repo root.
4. Make sure the agent reads `AGENTS.md` and `schema/AGENT.md`.
5. Tell the agent: `INGEST: raw/<file>`.
6. Review the generated wiki notes.
7. Run `LINT` periodically.
8. Run `AUDIT` after several ingests to improve the schema.

## Recommended First Ingest

Add one non-sensitive source under `raw/web/` or `raw/papers/`, then run:

```text
INGEST: raw/path-to-source.md
```

After the first ingest, check:

- `wiki/sources/`
- `wiki/concepts/`
- `wiki/entities/`
- `wiki/index.md`
- `wiki/log.md`

If the source was substantial, check:

- `schema/evolution/schema-proposals/`
- `schema/evolution/extraction-patterns.md`

## First 30 Minutes

Use this sequence for a clean first run:

1. Add one source:

```text
raw/web/my-first-source.md
```

2. In your agent CLI:

```text
Read AGENTS.md and schema/AGENT.md.
INGEST: raw/web/my-first-source.md
```

3. Review the generated source note.
4. Review any new concept or entity pages.
5. Ask:

```text
AUDIT the first ingest. What was good, what was weak, and what should the schema learn?
```

That last step is what makes this an operating system rather than a passive notes folder.

## Public Repo Safety

Before publishing:

- confirm `raw/` contains no private documents
- confirm `wiki/` contains no personal notes
- confirm `schema/evolution/personal-thinking-model.md` is still generic
- remove `.obsidian/workspace*` if Obsidian creates local workspace state
- never commit credentials, chat exports, medical records, tax files, contracts, screenshots, or private PDFs

This template's `.gitignore` is intentionally conservative around local app state and source archives.

## License

Use the included MIT License if you want others to freely reuse and adapt the framework.
