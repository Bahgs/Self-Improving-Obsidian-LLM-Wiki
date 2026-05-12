---
title: Output Quality Rubric
tags:
  - schema
  - evolution
  - quality
created: 2026-05-12
updated: 2026-05-12
status: active
---

# Output Quality Rubric

Use this rubric to judge whether an ingest, query answer, concept page, source page, or analysis page is actually improving the vault.

## Good Source Notes

A good source note:

- Preserves the source's actual argument without flattening it into generic summary.
- Separates facts, claims, vendor positioning, speculation, and open questions.
- Links to existing entities, concepts, summaries, and analysis pages.
- Names the raw source path exactly and does not invent sources.
- Captures what is reusable for future queries.
- Includes `Open Questions` when uncertainty remains.
- Includes `Pull-Forward Questions` when the source has strategic or generative value.

## Bad Source Notes

A bad source note:

- Restates the title and obvious bullets without preserving the source's mechanism.
- Creates isolated pages that do not link into the graph.
- Treats marketing claims, empirical evidence, and personal interpretation as equal.
- Copies too much from the source instead of synthesizing.
- Creates many shallow concept pages that will not become useful graph nodes.
- Misses why the source matters to existing themes in the vault.

## Good Concept Notes

A good concept note:

- Defines a reusable idea in a way that can absorb future sources.
- Distinguishes local working definition from source-specific usage.
- Lists source-supported details rather than unsupported generalizations.
- Links to related concepts, entities, summaries, and source pages.
- Is narrow enough to be meaningful and broad enough to compound across sources.

## Bad Concept Notes

A bad concept note:

- Is just a renamed source summary.
- Duplicates an existing concept under slightly different wording.
- Has no durable reuse beyond a single source.
- Uses vague language that would not help future retrieval or synthesis.
- Links only to the source that created it and never becomes a graph bridge.

## Good Analysis

A good analysis page:

- Answers a reusable question or makes a durable comparison.
- Surfaces contradictions, missing evidence, strategic implications, or decision points.
- Makes clear what is supported by the wiki and what remains uncertain.
- Produces next actions, next questions, or better future ingest behavior when appropriate.

## Pull-Forward Quality

Good pull-forward output:

- Points to a next question the user likely would not have asked unaided.
- Is grounded in the source and current wiki context.
- Connects knowledge to a possible project, thesis, workflow, or research path.
- Makes the intended reader clear when ambiguity exists: `For Future Agents`, `For Schema`, or `For User`.
- Avoids empty prompts like "learn more about this topic."

Bad pull-forward output:

- Is generic.
- Is speculative without being labeled as such.
- Suggests work that is not connected to the source.
- Overfits one source into a permanent rule.
- Looks like homework for the user when the question is really meant as future LLM context.

