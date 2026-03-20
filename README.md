# docs-skills

This repository contains documentation-first skills to keep project knowledge organized and reusable.

It currently provides three skills:
- `docs-categorize`: classifies findings and updates into architecture, tech design, and knowledge documentation
- `docs-context-bootstrap`: loads architecture, tech design, and knowledge docs as task startup context
- `docs-init-from-empty`: initializes documentation files when the project has no docs baseline

## Skill Overview

### 1) docs-categorize

Classifies research findings and project updates into the right documentation targets.

What it does:
- Ensures the documentation structure exists (`docs/`, `docs/designs/`, `docs/knowledge/`)
- Maintains `docs/architecture.md` for architecture-level updates
- Writes technical design docs to `docs/designs/*.md`
- Updates existing `docs/designs/*.md` files first when the topic matches
- Writes facts and knowledge to `docs/knowledge/*.md`
- Splits mixed updates into architecture vs design vs knowledge outputs

Use when:
- You finish a major implementation or refactor
- You consolidate research or discussion outcomes
- You want to convert scattered findings into searchable docs

Expected output:
- Updated `docs/architecture.md`
- One or more `docs/designs/*.md` files
- One or more `docs/knowledge/*.md` files
- A short categorization summary (what was written where)

### 2) docs-context-bootstrap

Loads project context from documentation before implementation work begins.

What it does:
- Validates docs baseline with objective checks (directory and non-empty files)
- Invokes `docs-init-from-empty` when docs files are missing
- Reads `docs/architecture.md` (if it exists)
- Reads task-relevant files in `docs/designs/*.md`
- Reads task-relevant files in `docs/knowledge/*.md`
- Produces a short, actionable context summary

Baseline checks:
- `docs/` exists
- `docs/architecture.md` exists and is non-empty
- `docs/designs/` has at least one non-empty `.md` file
- `docs/knowledge/` has at least one non-empty `.md` file

Use when:
- Starting a new task
- Starting a new conversation
- You want Copilot responses grounded in documented project context

Expected output:
- A summary of architecture, design highlights, and task-relevant knowledge

### 3) docs-init-from-empty

Initializes documentation when a project has no docs files yet.

What it does:
- Ensures `docs/`, `docs/designs/`, and `docs/knowledge/` exist
- Generates `docs/architecture.md` if missing
- Creates baseline files in `docs/designs/` and `docs/knowledge/` when empty
- Uses evidence-first writing; when evidence is insufficient, marks assumptions and open questions explicitly

Use when:
- Starting documentation from scratch
- `docs-context-bootstrap` detects missing docs baseline

Expected output:
- Baseline architecture, design, and knowledge docs ready for follow-up updates

Recommended usage:
You can add this tool to session start hook.

## Suggested Workflow

1. Run `docs-context-bootstrap` to load project context.
2. If docs are missing, let it invoke `docs-init-from-empty` first.
3. Do implementation, research, or troubleshooting.
4. Run `docs-categorize` to persist new findings into docs.

This loop keeps documentation current and helps future tasks start with better context.

## Writing Guidelines

- Keep architecture notes concise, stable, and long-term maintainable.
- Keep knowledge files factual and searchable.
- Do not record unverified assumptions as confirmed facts.
