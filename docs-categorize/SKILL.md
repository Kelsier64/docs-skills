---
name: docs-categorize
description: 'Classify research findings and project updates into detailed and complete docs, including auto-writing and auto-updating tech design docs. Use it after completing major project updates, drafting implementation plans, consolidating web research, summarizing discoveries, or recording user-provided facts.'
argument-hint: 'Describe the research/update content and expected classification output'
---

# Docs Research Categorizer

## Purpose
Classify findings into detailed architecture, design, and knowledge documentation.

1. Update docs/architecture.md 
- high-level design decisions, system structure, component interactions, architectural patterns, and rationale etc

2. Write to docs/designs/*.md for implementation design content:
- feature or task level technical design
- problem statement, goals/non-goals, constraints, options, chosen approach
- API/data model changes, rollout, risks, test plan
- prefer updating an existing topic file if one already matches the feature/task
- create a new file only when no existing topic file matches

3. Write to docs/knowledge/*.md for facts/knowledge:
- environment facts, workflow constraints, commands
- user-provided or web-search domain knowledge

4. If an update contains multiple types, split it:
- architecture parts go to docs/architecture.md
- implementation design parts go to docs/designs/*.md
- fact/knowledge parts go to one or more docs/knowledge/*.md files

## Procedure
1. Ensure docs/, docs/designs/, and docs/knowledge/ exist before writing.
2. Read the findings.
3. Split into architecture vs design vs knowledge.
4. Update docs/architecture.md with structured sections, rationale, constraints, and decision trade-offs.
5. Update docs/designs/*.md with implementation-ready details, including goals/non-goals, interfaces, data impact, rollout, risks, and validation plan.
6. For design docs, locate the most relevant existing file by topic and update it first; only create a new file when needed.
7. Update docs/knowledge/*.md with confirmed facts.
8. Make a clear, searchable filename based on topic.

## Output Contract
For each run, produce:
- Updated docs/architecture.md section entries as needed.
- Updated docs/designs/*.md files for task/feature technical design when matching files exist.
- One or more new docs/designs/*.md files only when no matching design file exists.
- One or more docs/knowledge/*.md files for user facts/knowledge, with topic-relevant filenames.
- A short summary of what was categorized and where.

## Completion Checklist
- Content is categorized (not dumped).
- Missing docs/ structure is created before writing.
- Architecture updates are in docs/architecture.md.
- Tech design updates are in docs/designs/*.md.
- Existing design docs are updated before creating new ones.
- User-provided facts are in docs/knowledge/*.md.
- Written docs are detailed, structured, and actionable.
- No speculative claims are written as facts.
