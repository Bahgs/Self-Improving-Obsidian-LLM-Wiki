---
name: obsidian-markdown
description: Create and edit Obsidian-flavored markdown with frontmatter, wikilinks, embeds, callouts, and internal note conventions.
---

# Obsidian Markdown Skill

Use this skill when creating or editing `.md` files in the vault.

Rules:

- Use YAML frontmatter for durable wiki pages.
- Use `[[wikilinks]]` for internal links.
- Use path-based wikilinks when clarity matters, such as `[[concepts/example-concept]]`.
- Use Markdown links for external URLs.
- Use `source_paths` only for raw files that actually exist.
- Keep pages focused and graph-friendly.

Common frontmatter:

```yaml
---
title: Human Readable Title
tags:
  - concept
created: YYYY-MM-DD
updated: YYYY-MM-DD
source_paths:
  - raw/path/to/source.md
status: active
---
```

