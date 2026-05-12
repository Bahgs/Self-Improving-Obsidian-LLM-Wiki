# Schema Proposals

Use this folder for proposed behavior changes that should be tested before becoming permanent rules.

Suggested format:

```markdown
---
title: Proposal Title
tags:
  - schema
  - proposal
created: YYYY-MM-DD
updated: YYYY-MM-DD
status: proposed
source_paths:
  - raw/path/to/source
---

# Proposal Title

## Trigger

What source, query, audit, or repeated failure caused this proposal?

## Proposed Change

What should future agents do differently?

## Why

Why is this useful?

## Risks

What could go wrong?

## Guardrails

How should future agents avoid overusing this rule?

## Promotion Rule

When should this become part of `schema/AGENT.md`?
```
