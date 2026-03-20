---
name: docs-context-bootstrap
description: 'Load architecture, tech design, and knowledge docs as startup context. If docs files are missing, invoke docs-init-from-empty first, then continue reading docs/architecture.md, docs/designs/*.md, and docs/knowledge/*.md.'
argument-hint: 'Optional: focus area keywords to prioritize while reading docs context'
---

# Docs Context Bootstrap

## Purpose
Load project context from architecture, tech design, and knowledge docs at the start of work.

## Procedure
1. Validate baseline with objective checks:
	- docs/ exists
	- docs/architecture.md exists and is non-empty
	- docs/designs/ has at least one non-empty .md file
	- docs/knowledge/ has at least one non-empty .md file
2. If any baseline check fails, invoke **docs-init-from-empty** skill first.
3. Read docs/architecture.md if it exists.
4. Read task related files in docs/designs/*.md if they exist.
5. Read task related files in docs/knowledge/*.md if they exist.
6. Summarize relevant points before implementation.

## Output
- Short context summary based on architecture + design + knowledge docs.
