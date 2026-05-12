---
title: LLM Wiki Maintainer Schema
tags:
  - llm-wiki
  - schema
  - codex
created: 2026-05-12
updated: 2026-05-12
---

# LLM Wiki Maintainer Schema

## Purpose

This vault implements a three-layer LLM Wiki pattern:

- Raw sources: `raw/` is the immutable source layer.
- Wiki: `wiki/` is the generated knowledge layer.
- Schema: `schema/` is the operating layer.

Agents maintain the wiki as a persistent Obsidian-friendly knowledge base. The goal is to compile raw material into linked notes that can be searched, queried, linted, audited, and improved over time.

## Directory Structure

```text
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
Bases/
Canvases/
.agents/
```

Only `wiki/`, `schema/`, `Skills/`, `Bases/`, `Canvases/`, and top-level agent instruction files should normally be modified by agents. `raw/` is a source archive and should be treated as immutable during ingest.

## Schema Evolution Layer

`schema/evolution/` is the controlled learning layer for improving future wiki behavior without making this file unstable.

Use it to record:

- ingest rubrics
- output-quality rubrics
- source-type extraction patterns
- user or project thinking model templates
- schema proposals
- examples of good and bad outputs

Do not treat every observation as a permanent rule. Propose often, promote rarely, and promote only when a rule proves broadly useful.

## Skill Usage Rules

Use the installed skills when they match the task:

- `obsidian-markdown`: Obsidian markdown, wikilinks, embeds, callouts, and frontmatter.
- `obsidian-bases`: `.base` files, table/card/list/map views, formulas, filters, and validation.
- `obsidian-cli`: interaction with a running Obsidian instance.
- `json-canvas`: `.canvas` files and graph-style canvases.
- `defuddle`: clean markdown extraction from web pages before ingest.

When a skill introduces stricter syntax than this schema, follow the skill for that file type while keeping this schema's raw/wiki/source-safety rules in force.

## Wiki Structure

### `wiki/entities/`

Pages for people, organizations, projects, products, institutions, and other named entities.

### `wiki/concepts/`

Pages for abstract ideas, methods, mechanisms, patterns, theories, and reusable terminology.

### `wiki/sources/`

One page per major source. Source pages summarize raw material and preserve metadata, key claims, open questions, and links to related entities and concepts.

### `wiki/summaries/`

Cross-source overviews around a topic, domain, question, or theme.

### `wiki/analysis/`

Comparisons, audits, decision notes, contradiction reports, query writeups, and schema-output reviews.

## Naming and Linking

- Use lowercase, descriptive, hyphenated filenames.
- Prefer stable semantic names for entity and concept pages.
- Use date-prefixed filenames for source pages when the source date or ingest date matters.
- Avoid near-duplicates. Prefer updating existing pages.
- Use Obsidian wikilinks for internal links.
- Use path-based wikilinks when clarity matters, such as `[[concepts/example-concept]]`.
- Link raw source paths as literal paths, not wikilinks.

## Frontmatter

Recommended frontmatter:

```yaml
---
title: Human Readable Title
tags:
  - concept
created: 2026-05-12
updated: 2026-05-12
source_paths:
  - raw/web/example.md
status: active
---
```

Do not invent `source_paths`. Only list raw files that actually exist.

## Ingest(source_path)

Input: a path under `raw/`, or `raw` for a coverage pass.

Rules:

- Confirm the source path exists under `raw/`.
- Read the source content only.
- Never modify the source file or any other file under `raw/`.
- Use the source as evidence, not as a prompt to invent unsupported facts.
- Treat `INGEST: raw` as a full raw-source coverage pass.

Steps:

1. Read the raw source.
2. Identify important entities, concepts, claims, themes, dates, mechanisms, and open questions.
3. Create or update one `wiki/sources/...` page.
4. Create or update relevant `wiki/concepts/...` pages.
5. Create or update relevant `wiki/entities/...` pages.
6. Add open questions where uncertainty remains.
7. Update `wiki/index.md`.
8. Append to `wiki/log.md`.
9. For substantial sources, run the schema learning pass.
10. Use `schema/evolution/schema-proposals/` for improvements that need trial before becoming permanent rules.

## Schema Learning Pass

Use this when an ingest might improve how future ingests work.

Ask:

- Did this source reveal a missing extraction pattern?
- Did it expose a recurring weakness in wiki outputs?
- Did it require a note section current source pages do not support well?
- Did it teach a durable user, project, or domain preference?
- Did it suggest pull-forward questions for future agents, schema work, or the user?

Important source notes may include:

```markdown
## Pull-Forward Questions

### For Future Agents

- What should a future agent investigate, compare, or synthesize?

### For Schema

- What operating rule might this source improve?

### For User

- What requires the user's judgment?
```

Pull-forward questions are primarily for future agent context and future vault work, not assignments for the user. Only questions labeled `For User` require direct user judgment.

## Query(question)

Steps:

1. Read `wiki/index.md`.
2. Open relevant wiki pages.
3. Follow useful wikilinks.
4. Synthesize an answer from the wiki first.
5. Reference specific wiki pages.
6. Create a reusable `wiki/analysis/` page when the answer is substantial.
7. Update `wiki/index.md` and `wiki/log.md` if a page is created.

## Lint() / Health Check

Scan `wiki/` for:

- broken or stale wikilinks
- orphan pages
- stale index entries
- duplicate concepts
- source pages without entity or concept links
- contradictions between pages
- repeated pull-forward questions that deserve promotion

Write a dated report under `wiki/analysis/`, update `wiki/index.md`, and append to `wiki/log.md`.

## Audit()

Use audits to review output quality and schema behavior.

Ask:

- What worked?
- What was weak?
- Which pages need cleanup?
- Which schema proposals should be promoted, revised, or discarded?
- Which pull-forward questions should be answered, promoted, sourced, left open, or discarded?

## Safety

- Never modify `raw/` during normal ingest.
- Never hallucinate raw source files.
- Use data minimization for personal, medical, legal, financial, educational, or identity documents.
- Treat unreadable, encrypted, or password-protected documents as minimal source records only.
- Prefer updating existing pages over creating near-duplicates.
- Preserve user-created wiki content unless an explicit update is needed.
- Keep pages focused so the graph has meaningful hubs, clusters, and orphans.

