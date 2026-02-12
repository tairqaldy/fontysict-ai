---
name: explain-concept
description: Explain a concept in the context of the S2 SDE course
argument-hint: Concept to explain
---

# Concept Explanation for SDE Study

## Context

Read the course context from CLAUDE.md in this repository root.

Search the knowledge base in these directories for relevant content:
- resources/ (analysis, design, implementation, manage-and-control)
- skills/ (professional, software-development: analysis, design, implementation, manage-and-control)
- learning-outcomes/detailed-criteria.md (for LO connections)

## Task

Explain the requested concept in the context of the S2 SDE course. You should:

1. **Explain the concept** clearly, assuming the student has completed Semester 1
2. **Use C# / ASP.NET examples** (the course tech stack) unless another language is specified
3. **Connect to learning outcomes** - explain which LO this concept falls under
4. **Provide a practical example** relevant to the student's projects if possible
5. **Reference the knowledge base** - point to specific files where the student can read more
6. **Suggest practice** - what the student could build or try to solidify understanding

Keep explanations practical and applied. Use analogies when helpful. If the knowledge base has content on this topic, incorporate it.

Concept to explain: ${input:query:e.g. SOLID, dependency injection, layered architecture...}
