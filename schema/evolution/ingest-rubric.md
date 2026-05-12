---
title: Ingest Rubric
tags:
  - schema
  - evolution
  - ingest
created: 2026-05-12
updated: 2026-05-12
status: active
---

# Ingest Rubric

This rubric extends `schema/CODEX.md`. The raw/wiki/schema separation remains the governing rule.

Use this rubric during substantial ingests, especially sources that introduce a new domain, recurring theme, research method, preference, or output-quality lesson.

## Source Reading

- Identify the source type: research paper, vendor essay, documentation, financial report, personal memory export, project sketch, article, transcript, legal/medical/financial record, or mixed source.
- Identify the author's intent: empirical research, product positioning, operational instruction, conceptual argument, personal memory, project documentation, or reference material.
- Separate evidence from interpretation.
- Preserve strong claims, but label vendor claims, unsupported predictions, and personal preferences clearly.
- Note temporal context when it matters.

## Knowledge Extraction

- Extract named entities, products, institutions, people, projects, and organizations.
- Extract reusable concepts, mechanisms, taxonomies, methods, and decision frameworks.
- Extract claims, findings, constraints, contradictions, and open questions.
- Link to existing wiki pages before creating new pages.
- Prefer updating a strong existing concept over creating a shallow near-duplicate.
- Create a new concept page only when the idea is reusable across sources or likely to become a durable graph hub.

## Personal or Project Relevance

- Ask whether the source teaches something durable about the user's interests, working style, decision patterns, project theses, research taste, or communication preferences.
- Add user-facing or project-facing lessons only when they are supported by the source or existing wiki pages.
- Avoid turning every interesting idea into a claimed preference. Use open questions when unsure.

## Pull-Forward Questions

For important sources, generate questions that help the vault act like a Knowledge as a Service system:

- What should this source make a future agent ask next?
- What adjacent source would validate, sharpen, or challenge this source?
- What wiki concept is underdeveloped because of this source?
- What project, thesis, workflow, or research path does this source point toward?
- What would be easy to summarize but strategically important to notice?

Pull-forward questions should be specific, source-grounded, and useful for future work.

### Intended Reader

Pull-forward questions are primarily for future LLM context and future query/ingest work. They are not assignments for the user unless explicitly labeled `For User`.

Use audience labels when useful:

- `For Future Agents`: latent prompts that a future agent can answer, expand, or turn into analysis pages.
- `For Schema`: possible operating-rule or rubric improvements.
- `For User`: questions that require the user's judgment, taste, or lived context.

### Lifecycle

Pull-forward questions should not accumulate forever as decorative prompts.

During substantial query work, lint checks, or schema-output audits:

- answer the question directly if it is now relevant
- promote it into a `wiki/analysis/` page if it deserves reusable synthesis
- promote it into `schema/evolution/schema-proposals/` if it suggests an operating-rule change
- turn it into a source wishlist if it requires outside evidence
- leave it open if it is useful but premature
- discard it if it proves generic or low-value

Use explicit status markers only when helpful, such as `open`, `answered`, `promoted`, `source-needed`, or `discarded`.

## Schema Learning Pass

At the end of a substantial ingest, ask:

- Did this source reveal a missing extraction pattern?
- Did this source require a section that current source notes do not support well?
- Did it expose a recurring weakness in wiki outputs?
- Did it suggest a new quality criterion for summaries, concepts, or analysis pages?
- Did it reveal a durable user or project preference that belongs in the schema?
- Should this lesson become a schema proposal instead of an immediate rule?

Only update `schema/CODEX.md` directly for stable, broadly applicable behavior changes. Use `schema/evolution/schema-proposals/` for ideas that need trial and review.

