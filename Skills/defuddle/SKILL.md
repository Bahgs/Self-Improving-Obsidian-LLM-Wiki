---
name: defuddle
description: Extract clean markdown from web pages before ingesting or analyzing online sources.
---

# Defuddle Skill

Use this skill when the user provides a web URL and wants it ingested or analyzed.

Workflow:

1. Extract the page into clean markdown.
2. Save or reference the clean source under `raw/web/` if the user wants it archived.
3. Ingest from the cleaned raw source.

Do not use this for URLs that already point directly to markdown files.

