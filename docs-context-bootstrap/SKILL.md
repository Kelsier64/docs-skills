---
name: docs-context-bootstrap
description: 'Load architecture and knowledge docs as startup context. Use when a conversation should begin with project architecture and knowledge facts from docs/architecture.md and docs/knowledge/*.md.'
argument-hint: 'Optional: focus area keywords to prioritize while reading docs context'
---

# Docs Context Bootstrap

## Purpose
Load project context from architecture and knowledge docs at the start of work.

## Procedure
1. Read docs/architecture.md if it exists.
2. Read task related files in docs/knowledge/*.md if they exist.
3. Summarize relevant points before implementation.

## Output
- Short context summary based on architecture + knowledge docs.
