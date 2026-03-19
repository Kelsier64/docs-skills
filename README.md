# docs-skills

This repository contains documentation-first skills to keep project knowledge organized and reusable.

It currently provides two skills:
- `docs-categorize`: classifies findings and updates into architecture and knowledge documentation
- `docs-context-bootstrap`: loads architecture and knowledge docs as task startup context

## Skill Overview

### 1) docs-categorize

Classifies research findings and project updates into the right documentation targets.

What it does:
- Ensures the documentation structure exists (`docs/`, `docs/knowledge/`)
- Maintains `docs/architecture.md` for architecture-level updates
- Writes facts and knowledge to `docs/knowledge/*.md`
- Splits mixed updates into architecture vs knowledge outputs

Use when:
- You finish a major implementation or refactor
- You consolidate research or discussion outcomes
- You want to convert scattered findings into searchable docs

Expected output:
- Updated `docs/architecture.md`
- One or more `docs/knowledge/*.md` files
- A short categorization summary (what was written where)

### 2) docs-context-bootstrap

Loads project context from documentation before implementation work begins.

What it does:
- Reads `docs/architecture.md` (if it exists)
- Reads task-relevant files in `docs/knowledge/*.md`
- Produces a short, actionable context summary

Use when:
- Starting a new task
- Starting a new conversation
- You want Copilot responses grounded in documented project context

Expected output:
- A summary of architecture highlights and task-relevant knowledge

Recommended usage:
You can add this tool to session start hook.

## Suggested Workflow

1. Run `docs-context-bootstrap` to load project context.
2. Do implementation, research, or troubleshooting.
3. Run `docs-categorize` to persist new findings into docs.

This loop keeps documentation current and helps future tasks start with better context.

## Writing Guidelines

- Keep architecture notes concise, stable, and long-term maintainable.
- Keep knowledge files factual and searchable.
- Do not record unverified assumptions as confirmed facts.
