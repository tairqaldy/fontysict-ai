---
name: check-learning-outcomes
description: Check learning outcomes coverage across project repos
argument-hint: Which repos to check (or "all current")
---

# Learning Outcomes Coverage Check

## Context

Read from the knowledge base (this repo root):
- CLAUDE.md
- learning-outcomes/overview.md
- learning-outcomes/detailed-criteria.md
- course-info/assessment.md

## Task

Analyze the student's current work across their project repositories and map it against the SDE learning outcomes.

Project repos to check (sibling folders under fontys-projects/):
- Look for all directories that appear to be S2 projects (not S1 legacy repos)
- The student will tell you which repos are current

For each learning outcome:

| Learning Outcome | Status | Evidence Found | Gaps | Next Step |
|-----------------|--------|---------------|------|-----------|
| ... | No Evidence / Partial / Sufficient / Strong | What specific work demonstrates this LO | What is missing | Concrete action to strengthen evidence |

After the table, provide:
1. **Top 3 priority actions** - the most impactful things to work on next
2. **Portfolio suggestions** - how to present the existing evidence effectively
3. **Risk assessment** - which LOs are at risk of being insufficient by the next iteration

${input:query:Which project repos to check? (e.g. "individual-project" or "all current")}
