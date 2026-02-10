# Fontys ICT - Semester 2: Software Design & Engineering (SDE)

## What This Repository Is

This is a knowledge base extracted from Canvas LMS for the S2 SDE course at Fontys University of Applied Sciences (HBO, Netherlands). It contains course materials, assessment criteria, learning resources, and project descriptions organized as markdown files. Claude Code agents should use this as their primary reference for understanding course requirements and standards.

## Course Overview

- **Program:** Fontys ICT (HBO University of Applied Sciences, Eindhoven, Netherlands)
- **Semester:** 2
- **Course:** Software Design & Engineering (SDE)
- **Duration:** ~20 weeks (February - July 2026)
- **Language:** English (international track)
- **Tech Stack:** C#, ASP.NET, HTML/CSS, Bootstrap, SQL/Relational Databases
- **Methodology:** Portfolio-based assessment, iterative development

## Learning Outcomes

The S2 SDE course assesses students on these 6 learning outcomes:

| LO | Name | Definition (condensed) |
|----|------|------------------------|
| **1** | Analysis | Analyze and document validated user specifications based on stakeholder feedback and according to a standard method for simple, non-distributed applications. |
| **2** | Design | Methodically translate validated user specifications into software and database designs, considering maintainability and security. Justify your choices. |
| **3** | Implementation | Build and deliver multiple secure and maintainable applications (at least one web-based) iteratively. Apply OOP and SOLID principles. Use a relational database for persistence. |
| **4** | Managing | Use version control, (automated) testing, and an iterative process to improve code quality. Explain how chosen techniques contribute to improvement. |
| **5** | Professional Standard | Apply professional practice in project organisation, communication with stakeholders, exploratory research, and reporting. |
| **6** | Personal Leadership | Take the initiative in asking for and reflecting on feedback. Identify core values as the basis for study career and professional development. |

**Full definitions and clarifications:** [learning-outcomes/detailed-criteria.md](learning-outcomes/detailed-criteria.md)

## Rubric

| Level | Name | Meaning |
|-------|------|---------|
| 0 | Undefined | No evidence or not yet assessed |
| 1 | Orienting | Beginning to understand; limited evidence |
| 2 | Beginning | Developing capability; partial evidence |
| 4 | Proficient | Meets expectations; sufficient evidence |
| 5 | Advanced | Exceeds expectations; strong evidence |

**Assessment guarantee:** If you achieve at least **Proficient** on all learning outcomes at the end of the semester, you are guaranteed a **Satisfactory** grade or better (USGO scale).

## Assessment Structure & Dates (S2 2025–2026)

| Moment | Type | Date | Related Page |
|--------|------|------|--------------|
| First Portfolio Review | Practice review | **Fri Mar 6, 2026 – 17:00** | [portfolio/first-portfolio-review.md](portfolio/first-portfolio-review.md) |
| Iteration 1 | Iteration snapshot | **Fri Mar 20, 2026 – 17:00** | [portfolio/iteration-1.md](portfolio/iteration-1.md) |
| Iteration 2 | Iteration snapshot | **Fri Apr 17, 2026 – 17:00** | [portfolio/iteration-2.md](portfolio/iteration-2.md) |
| Iteration 3 | Iteration snapshot | **Fri May 22, 2026 – 17:00** | [portfolio/iteration-3.md](portfolio/iteration-3.md) |
| Final Delivery | Final delivery & assessment | **Thu Jun 18, 2026 – 17:00** | [portfolio/final-delivery-assessment.md](portfolio/final-delivery-assessment.md) |
| Final Interview | Oral assessment | **Week 18** | [course-info/assessment.md](course-info/assessment.md) |
| Assessment Committee | Final grading | **Week 19** | [course-info/assessment.md](course-info/assessment.md) |

## Project Repositories

The student's actual code lives in sibling repositories under:
`C:\Users\tairc\Documents\codespace\fontys-projects\`

### Current S2 Projects

| Folder | Purpose | Status |
|--------|---------|--------|
| `circus-train-challenge-1st-week-orienting` | Jumpstart algorithmic challenge (week 1) | Active |
| *(Individual Project repo - TBD)* | Main individual project | Not yet created |
| *(Group Project repo - TBD)* | Group project | Not yet created |

When helping with code, always consider which project repo is relevant and what learning outcomes the work demonstrates.

## Code Standards for SDE Course

When reviewing code or helping with implementation, apply these standards:

### Object-Oriented Programming

- Proper use of classes, inheritance, interfaces, polymorphism
- Encapsulation (private fields, public properties/methods)
- Single Responsibility at the class level
- Favor composition over inheritance where appropriate

### SOLID Principles

- **S**ingle Responsibility Principle - a class should have one reason to change
- **O**pen/Closed Principle - open for extension, closed for modification
- **L**iskov Substitution Principle - subtypes must be substitutable for their base types
- **I**nterface Segregation Principle - prefer specific interfaces over general-purpose ones
- **D**ependency Inversion Principle - depend on abstractions, not concretions

### Layered Architecture

- **Presentation Layer** - ASP.NET MVC / Razor Pages (controllers, views)
- **Business Logic Layer** - Domain models, services, validation
- **Data Access Layer** - Repositories, database context, Entity Framework
- Clear separation of concerns between layers
- Dependencies flow downward only (Presentation -> Business -> Data Access)

### C# / ASP.NET Conventions

- PascalCase for public members, camelCase for private fields (prefix with `_`)
- Use dependency injection (built-in ASP.NET DI container)
- Exception handling with meaningful messages
- Async/await for I/O operations
- Follow Microsoft C# coding conventions

### Unit Testing

- Arrange-Act-Assert pattern
- Test business logic independently from data access
- Meaningful test names that describe the scenario and expected result
- Mock dependencies using interfaces

### Database Design

- Normalized relational database design (at least 3NF)
- Proper use of primary keys and foreign keys
- Meaningful table and column names
- SQL queries and/or Entity Framework for data access

### Git & Version Control

- Meaningful commit messages describing what and why
- Feature branches for new work
- Regular commits showing iterative progress
- Clean commit history

## Portfolio Guidance

The portfolio is the primary assessment artifact. It must:

- Demonstrate all learning outcomes with concrete evidence
- Show iterative progress (not just final results)
- Include reflection on the learning process
- Reference actual project work from the project repos
- Be reviewed at each iteration checkpoint

**Key portfolio files:** [portfolio/portfolio-manual.md](portfolio/portfolio-manual.md), [portfolio/creating-a-portfolio.md](portfolio/creating-a-portfolio.md), [portfolio/review-iterations.md](portfolio/review-iterations.md)

## DOT Framework (Research)

The course uses the DOT (Development Oriented Triangulation) Framework for research:

- **Library:** Literature study, available product analysis, community research, best/good/bad practices
- **Field:** Observation, interview, survey, focus group, problem analysis
- **Lab:** Component test, A/B test, system test, usability test, security test
- **Showroom:** Peer review, expert review, product review
- **Workshop:** Prototyping, brainstorm, co-creation, multi-criteria decision making

Research documents should use multiple strategies from different categories (triangulation) to support conclusions.

**Details:** [skills/professional/dot-framework.md](skills/professional/dot-framework.md)

## Knowledge Base Structure

| Folder | Contents |
|--------|----------|
| `course-info/` | Course overview, project descriptions, assessment criteria |
| `portfolio/` | Portfolio creation guide, manual, iteration schedule |
| `learning-outcomes/` | Learning outcome descriptions and criteria |
| `resources/` | Theory/reference material (analysis, design, implementation, manage & control) |
| `skills/professional/` | Professional skills guides (research, feedback, planning, etc.) |
| `skills/software-development/` | Practical how-to guides for technical skills |
| `jumpstart/` | First 2 weeks material |
| `extra/` | Supplementary material (challenges, AI manifest, Student+) |

## Quick Reference for Agents

Use this mapping when students ask common questions:

| Question / Topic | Primary Files |
|------------------|---------------|
| **Learning outcomes** – what do I need to demonstrate? | `learning-outcomes/overview.md`, `learning-outcomes/detailed-criteria.md` |
| **Portfolio** – how do I build it? | `portfolio/portfolio-manual.md`, `portfolio/creating-a-portfolio.md` |
| **Portfolio dates** – when are reviews? | `portfolio/review-iterations.md` |
| **Portfolio iterations** – what for each? | `portfolio/first-portfolio-review.md`, `portfolio/iteration-1.md`, `portfolio/iteration-2.md`, `portfolio/iteration-3.md`, `portfolio/final-delivery-assessment.md` |
| **Assessment** – how am I graded? | `course-info/assessment.md` |
| **Individual project** | `course-info/individual-project.md` |
| **Group project** | `course-info/group-project.md` |
| **Extra project / challenges** | `course-info/extra-project.md`, `extra/container-transport.md`, `extra/visitor-placement-tool.md` |
| **SOLID principles** | `skills/software-development/design/solid-in-practice.md`, `resources/design/solid-principles.md` |
| **Layered architecture** | `resources/design/layered-architecture.md` |
| **Unit testing** | `skills/software-development/implementation/unit-testing-practice.md`, `skills/software-development/implementation/acceptance-unit-testing.md` |
| **Dependency injection** | `skills/software-development/implementation/dependency-injection-aspnet.md` |
| **Statefulness / sessions** | `skills/software-development/implementation/application-statefulness.md` |
| **Research (DOT)** | `skills/professional/dot-framework.md`, `skills/professional/research.md` |
| **Documentation** | `skills/professional/documentation.md` |
| **Planning / iterations** | `skills/professional/planning-iterations.md` |
| **Feedback** | `skills/professional/feedback.md` |
| **AI usage** | `extra/generative-ai-manifest.md` |

## How to Use This Repo with Agents

1. **`/question`** – General-purpose entry point for students to ask about project, program, schedule, assignments, etc. Provide concise answers with references and offer to clarify terminology.
2. **Always reference specific learning outcomes** when giving advice
3. **Point to relevant knowledge base files** when explaining concepts (use the Quick Reference above)
4. **Apply SDE code standards** (SOLID, layered architecture, C# conventions) in all code help
5. **Consider portfolio evidence** – suggest how work can demonstrate learning outcomes
6. **Be practical** – this is HBO (applied sciences), focus on working software over theory
7. **Check the project repos** for actual code context when helping with implementation
8. **Use the DOT framework** when helping with research tasks
9. **Respect the iteration cycle** – help plan work that fits the current iteration's goals
10. **Link guidance:** Use local markdown when content exists here. **Canvas/Fontys URLs are fine** – primary users (students, teachers) have access to Fontys infrastructure and Canvas; use them when they add value (e.g. live discussions, assignments, Canvas-specific tools)
