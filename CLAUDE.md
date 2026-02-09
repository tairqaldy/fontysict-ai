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

<!-- PRIORITY: Update this section with exact LO descriptions from learning-outcomes/overview.md once extracted -->

The S2 SDE course assesses students on these learning outcome areas:

1. **Analysis** - Requirements engineering, use cases, conceptual modeling
2. **Design** - Architecture (layered), OOP, SOLID, class diagrams, database design
3. **Implementation** - Clean code in C#/ASP.NET, database implementation, unit testing
4. **Manage & Control** - Git, debugging, deployment
5. **Professional Skills** - Planning, feedback, research (DOT framework), documentation

## Assessment Structure

- Portfolio-based assessment with 3 review iterations + final delivery
- Each iteration reviews progress on learning outcomes
- Final assessment grades all learning outcomes
- Must demonstrate evidence across Individual Project and Group Project

<!-- PRIORITY: Update with exact dates, criteria, and rubric from course-info/assessment.md -->

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

<!-- PRIORITY: Update with exact requirements from portfolio/portfolio-manual.md -->

## DOT Framework (Research)

The course uses the DOT (Development Oriented Triangulation) Framework for research:

- **Library:** Literature study, available product analysis, community research, best/good/bad practices
- **Field:** Observation, interview, survey, focus group, problem analysis
- **Lab:** Component test, A/B test, system test, usability test, security test
- **Showroom:** Peer review, expert review, product review
- **Workshop:** Prototyping, brainstorm, co-creation, multi-criteria decision making

Research documents should use multiple strategies from different categories (triangulation) to support conclusions.

<!-- PRIORITY: Update with details from skills/professional/dot-framework.md -->

## Knowledge Base Structure

Content extracted from Canvas is organized in these folders:

| Folder | Contents |
|--------|----------|
| `course-info/` | Course overview, project descriptions, assessment criteria |
| `portfolio/` | Portfolio creation guide, manual, iteration schedule |
| `learning-outcomes/` | Learning outcome descriptions and criteria |
| `resources/` | Theory/reference material (analysis, design, implementation, manage & control) |
| `skills/professional/` | Professional skills guides (research, feedback, planning, etc.) |
| `skills/software-development/` | Practical how-to guides for technical skills |
| `jumpstart/` | First 2 weeks material |
| `extra/` | Supplementary material |

## Content Extraction Priority

Files marked with status indicate whether Canvas content has been pasted in yet.
Extract in this order for maximum benefit:

### Priority 1 - Extract ASAP
1. `course-info/assessment.md` - defines what success looks like
2. `learning-outcomes/overview.md` - foundation everything maps to
3. `course-info/overview.md` - course structure and expectations
4. `course-info/individual-project.md` - primary assessment vehicle
5. `portfolio/portfolio-manual.md` - how to build the portfolio

### Priority 2 - Extract in first 2 weeks
6. `course-info/group-project.md`
7. `portfolio/creating-a-portfolio.md`
8. `portfolio/review-iterations.md`
9. `skills/professional/dot-framework.md`
10. `skills/professional/research-document-template.md`

### Priority 3 - Extract as topics come up
11+. Core technical resources (SOLID, layered architecture, OOP, unit testing, ASP.NET, DI, etc.)

### Priority 4 - Extract when relevant
Remaining files as needed throughout the semester.

## How to Help This Student

1. **Always reference specific learning outcomes** when giving advice
2. **Point to relevant knowledge base files** when explaining concepts
3. **Apply SDE code standards** (SOLID, layered architecture, C# conventions) in all code help
4. **Consider portfolio evidence** - suggest how work can demonstrate learning outcomes
5. **Be practical** - this is HBO (applied sciences), focus on working software over theory
6. **Check the project repos** for actual code context when helping with implementation
7. **Use the DOT framework** when helping with research tasks
8. **Respect the iteration cycle** - help plan work that fits the current iteration's goals
