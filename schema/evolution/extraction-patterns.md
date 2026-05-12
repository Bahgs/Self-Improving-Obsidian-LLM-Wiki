---
title: Extraction Patterns
tags:
  - schema
  - evolution
  - extraction-patterns
created: 2026-05-12
updated: 2026-05-12
status: active
---

# Extraction Patterns

This file records reusable source-type strategies. Add patterns only when they improve repeated ingest quality.

## Research Papers

Extract:

- research question
- method or experimental setup
- datasets, benchmarks, or evaluation criteria
- key findings
- limitations
- claims that should update existing concepts
- links to related papers, labs, techniques, and open problems
- implications for future work or projects

Watch for:

- benchmark overgeneralization
- missing baselines
- claims that are stronger than the evidence
- concepts that deserve separation from paper-specific terminology

## Vendor Thesis Essays

Extract:

- core thesis
- product-positioning claims
- conceptual vocabulary introduced by the vendor
- market/category framing
- architectural assumptions
- comparison targets
- evidence gaps
- implications for existing wiki themes

Watch for:

- treating vendor claims as independent evidence
- missing the mechanism because the essay is rhetorically polished
- creating concept pages for branded language that is not reusable

## Enterprise Workflow AI Vendor Posts

Extract:

- fragmented workflow or system-of-record problem
- systems the AI must connect to
- claimed agent actions and human approval checkpoints
- operational risk, permissioning, and writeback constraints
- measurable outcomes the vendor implies but does not prove
- relation to context, ontology, data-integration, and KaaS concepts

Watch for:

- accepting workflow examples as proof of business impact
- missing governance details around writes, credentials, and customer data
- summarizing generic AI copy instead of extracting the concrete operating model

## AI Safety and Alignment Research

Extract:

- evaluated failure mode
- evaluation distribution and held-out or out-of-distribution checks
- intervention or training data used
- claimed generalization behavior
- persistence through later training or deployment changes
- limitations acknowledged by the source
- differences between direct behavior imitation and principle-based training

Watch for:

- evaluation overfitting
- first-party claims that need independent replication
- confusion between suppressing a measured failure and solving the broader risk
- examples that teach a schema lesson beyond the AI safety domain

## AI Economic Usage Reports

Extract:

- observed AI usage distribution by task, occupation, geography, platform, and use case
- distinction between adoption, augmentation, automation, autonomy, and task success
- methodology for transcript classification or privacy-preserving measurement
- job-exposure assumptions and weighting
- inequality, skill, education, regional, or productivity implications
- uncertainty windows and external validity limits

Watch for:

- treating one provider's usage as total AI adoption
- treating task coverage as successful automation
- ignoring platform differences between consumer chat and API traffic
- missing source-defined measurement primitives that should become reusable wiki concepts

## Investment Product and Manager Materials

Extract:

- product or strategy type
- manager thesis and how strongly it is evidenced
- index, benchmark, or portfolio construction rules
- fees, assets, holdings, concentration, and liquidity data when present
- risk disclosures and implementation constraints
- distinction between marketing claims, process descriptions, and independent evidence
- links to portfolio tracking, ETF liquidity, due diligence, and relevant investment themes

Watch for:

- treating product marketing as investment advice
- copying contact details or promotional language that does not improve the wiki
- missing ETF wrapper risks
- failing to preserve the point-in-time nature of holdings, AUM, rankings, and expense data

## Alternative Data and Social-Signal Research

Extract:

- signal source and what behavior it proxies
- target outcome and official comparison dataset
- spatial and temporal granularity
- model features, validation design, and reported performance
- representativeness, privacy, and platform-selection limits
- policy or operational use case

Watch for:

- treating a proxy as ground truth
- ignoring missing populations or platform adoption bias
- overgeneralizing a signal from one crisis, country, or platform to all forecasting problems

## Technical Documentation

Extract:

- API surfaces, required parameters, authentication, rate limits, object models, and workflows
- integration constraints
- operational gotchas
- examples that clarify real use
- links to existing project or implementation concepts

Watch for:

- copying documentation instead of extracting durable integration knowledge
- ignoring version, date, or endpoint differences
- failing to connect docs to existing projects that might use them

## Personal Memory Exports

Extract:

- durable preferences
- recurring projects
- repeated decision patterns
- communication style
- constraints that should affect future behavior
- themes that belong in concepts or analysis pages

Watch for:

- over-indexing ephemeral details
- copying sensitive or excessive personal data
- converting one-off comments into permanent preferences

## Project Sketches

Extract:

- problem
- target users
- workflow
- data sources
- product surface
- economic or operational thesis
- risks and validation questions
- links to concepts, entities, and similar projects

Watch for:

- summarizing the sketch without turning it into a reusable project or concept cluster
- missing obvious validation paths
- ignoring connections to existing project themes

