# LLM Wiki Framework

An Obsidian-friendly knowledge vault pattern for turning raw source material into a persistent, interlinked, agent-maintained wiki that improves its own operating rules over time.

This repo is a sanitized public template. It contains the framework, folder structure, agent instructions, schema, rubrics, and example skill docs. It intentionally contains no private raw files, generated personal notes, credentials, medical records, financial records, chat exports, or personal memory data.

## Why This Exists

The starting point is the LLM Wiki idea popularized by Andrej Karpathy: keep source material and generated knowledge in a persistent text system that an LLM can read, edit, and connect over time.

This framework keeps that foundation but adds a second idea:

> The wiki should not only grow in content. It should also improve the way future agents ingest, summarize, connect, and reason.

Most AI note systems get bigger. This one is designed to get more operationally intelligent. New sources can create new wiki pages, but they can also create schema proposals, output-quality lessons, extraction patterns, and future-agent prompts.

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
    CODEX.md
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
3. Point your coding or agent tool at the repo.
4. Tell the agent: `INGEST: raw/<file>`.
5. Review the generated wiki notes.
6. Run `LINT` periodically.
7. Run `AUDIT` after several ingests to improve the schema.

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

