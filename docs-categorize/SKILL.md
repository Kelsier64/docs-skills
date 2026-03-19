---
name: docs-categorize
description: 'Classify research findings and project updates into docs. Use it after completing major project updates, consolidating web research, summarizing discoveries, or recording user-provided facts.'
argument-hint: 'Describe the research/update content and expected classification output'
---

# Docs Research Categorizer

## Purpose
Quickly classify findings into architecture notes and knowledge notes.

## Classification Rules
0. Ensure docs structure exists before writing:
- if docs/ does not exist, create docs/
- if docs/knowledge/ does not exist, create docs/knowledge/
- if docs/architecture.md does not exist, scan the entire codebase and generate a comprehensive docs/architecture.md

1. Update docs/architecture.md 
- if docs/architecture.md does not exist, scan the entire codebase and generate it first

2. Write to docs/knowledge/*.md for facts/knowledge:
- environment facts, workflow constraints, commands
- user-provided or web-search domain knowledge

3. If an update contains both types, split it:
- architecture parts go to docs/architecture.md
- fact/knowledge parts go to one or more docs/knowledge/*.md files

## Procedure
1. Read the findings.
2. Ensure docs/ and docs/knowledge/ exist.
3. If docs/architecture.md does not exist, scan the entire codebase and generate it.
4. Split into architecture vs knowledge.
5. Update docs/architecture.md with concise bullets.
6. Update docs/knowledge/*.md with confirmed facts.
7. make a clear, searchable filename based on topic.

## Output Contract
For each run, produce:
- Updated docs/architecture.md section entries as needed.
- One or more docs/knowledge/*.md files for user facts/knowledge, with topic-relevant filenames.
- A short summary of what was categorized and where.

## Completion Checklist
- Content is categorized (not dumped).
- Missing docs/ structure is created before writing.
- Architecture updates are in docs/architecture.md.
- User-provided facts are in docs/knowledge/*.md.
- No speculative claims are written as facts.
