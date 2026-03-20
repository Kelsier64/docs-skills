---
name: docs-init-from-empty
description: 'Use when project docs are missing, specifically when the docs/ directory does not exist or when docs/architecture.md, docs/designs/*.md, and docs/knowledge/*.md are all absent.'
argument-hint: 'Optional: feature or domain keywords to seed initial doc structure'
---

# Docs Init From Empty

## Purpose
Create comprehensive and production-usable documentation for projects that have no docs files yet.

## Detail Standard
Generated docs must be specific, actionable, and implementation-usable.

Hard quality rules:
- Do not output placeholder-only sections.
- Do not leave TODO/TBD-only content as the final section body.
- Each required section must include concrete project-specific details and rationale.
- When evidence is insufficient, write only verified facts plus explicit assumptions/open questions.

Required sections for docs/architecture.md:
- System Overview
- Main Components and Responsibilities
- Data and Control Flow
- Key Architectural Decisions and Rationale
- Constraints, Risks, and Open Questions

Required sections for docs/designs/overview.md:
- Scope and Current Feature Areas
- Design Principles and Non-Goals
- Cross-Cutting Concerns (security, performance, reliability, observability)
- Planned Milestones
- Known Risks and Follow-Up Tasks

Required sections for docs/knowledge/project-facts.md:
- Environment and Tooling Facts
- Build/Test/Run Commands
- Repo Workflow Constraints
- Glossary and Domain Terms

## Procedure
1. Ensure docs/, docs/designs/, and docs/knowledge/ exist.
2. If docs/architecture.md is missing, generate it from a codebase scan using all required architecture sections; when evidence is limited, mark assumptions and unknowns explicitly.
3. If docs/designs/ has no files, create docs/designs/overview.md using all required design sections.
4. If docs/knowledge/ has no files, create docs/knowledge/project-facts.md using all required knowledge sections.
5. Return a concise summary of files created.

## Output Contract
For each run, produce:
- docs/architecture.md (created if missing)
- at least one file in docs/designs/
- at least one file in docs/knowledge/
- section-complete content in each created file with concrete details
- a short summary of what was created and why

## Completion Checklist
- Missing documentation directories are created.
- architecture, design, and knowledge comprehensive files exist after run.
- Created docs include required sections and actionable details.
- No unverified assumptions are written as facts.
