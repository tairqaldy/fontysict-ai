# Plan: Fontys ICT S2 SDE Canvas Knowledge Base

## What We're Building

A structured markdown knowledge base from Canvas LMS content + Claude Code slash commands + CLAUDE.md configuration, so Claude agents can help with assignments, portfolio, code reviews, and study throughout Semester 2.

## Key Facts

* **Course:** Software Design & Engineering (SDE), Semester 2, Fontys ICT (HBO, Netherlands)
* **Tech stack:** C#, ASP.NET, HTML/CSS, Bootstrap, SQL/Relational Databases
* **Assessment:** Portfolio-based, 3 review iterations + final delivery
* **Current project:** `circus-train-challenge-1st-week-orienting` (jumpstart assignment)
* **Future projects:** New repos will be created for Individual Project and Group Project
* **S1 repos exist** but are not relevant to this setup
* **Content extraction:** Manual copy-paste from Canvas into template markdown files

---

## Folder Structure to Create

```
second-semester-canvas-course-contents/
├── CLAUDE.md                           # Master context file (rewrite)
├── images/                             # (existing, keep as-is)
│
├── course-info/
│   ├── overview.md                     # First Introduction to SDE
│   ├── individual-project.md
│   ├── group-project.md
│   ├── extra-project.md
│   ├── workshop-schedule.md
│   └── assessment.md                   # "How do I get assessed?"
│
├── portfolio/
│   ├── creating-a-portfolio.md
│   ├── portfolio-manual.md
│   └── review-iterations.md            # Iteration 1-3 dates + final delivery
│
├── learning-outcomes/
│   └── overview.md                     # Introduction to Learning Outcomes
│
├── resources/
│   ├── analysis/
│   │   ├── functional-nonfunctional-requirements.md
│   │   ├── use-cases.md
│   │   ├── conceptual-model.md
│   │   └── acceptance-testing.md
│   ├── design/
│   │   ├── layered-architecture.md
│   │   ├── oop-principles.md
│   │   ├── solid-principles.md
│   │   └── class-diagram.md
│   ├── implementation/
│   │   ├── frontend-frameworks.md
│   │   ├── state-management.md
│   │   ├── unit-testing.md
│   │   ├── database-sql.md
│   │   └── exception-handling.md
│   └── manage-and-control/
│       ├── git-fundamentals.md
│       └── what-is-manage-and-control.md
│
├── skills/
│   ├── professional/
│   │   ├── planning-iterations.md
│   │   ├── feedback.md
│   │   ├── client-interaction.md
│   │   ├── cultural-awareness.md
│   │   ├── research.md
│   │   ├── research-document-template.md
│   │   ├── documentation.md
│   │   ├── dot-framework.md
│   │   └── guided-writing.md
│   └── software-development/
│       ├── analysis/
│       │   ├── creating-functional-nonfunctional-reqs.md
│       │   └── use-cases-and-conceptual-models.md
│       ├── design/
│       │   ├── conceptual-to-concrete-diagrams.md
│       │   ├── ui-wireframe-design.md
│       │   ├── functional-reqs-as-agreed.md
│       │   ├── solid-in-practice.md
│       │   ├── atomic-vs-rich-models.md
│       │   └── relational-db-design.md
│       ├── implementation/
│       │   ├── oop-in-practice.md
│       │   ├── html-css.md
│       │   ├── aspnet-bootstrap.md
│       │   ├── db-implementation.md
│       │   ├── relational-dbs.md
│       │   ├── dependency-injection-aspnet.md
│       │   ├── unit-testing-practice.md
│       │   ├── acceptance-unit-testing.md
│       │   └── application-statefulness.md
│       └── manage-and-control/
│           ├── debugging-csharp.md
│           └── aspnet-deployment.md
│
├── jumpstart/
│   ├── welcome-kickoff.md
│   ├── individual-project-prep.md
│   ├── good-in-practice.md
│   └── circus-train-kickstart.md
│
├── extra/
│   ├── software-path-fontys.md
│   ├── associate-degree.md
│   ├── generative-ai-manifest.md
│   ├── container-transport.md
│   ├── visitor-placement-tool.md
│   └── student-plus.md
│
└── .claude/
    └── commands/
        ├── help-assignment.md          # Understand assignment requirements
        ├── review-portfolio.md         # Portfolio review & guidance
        ├── review-code.md              # Code review against SDE standards
        ├── explain-concept.md          # Study/concept explanation
        ├── help-research.md            # DOT framework research help
        ├── plan-iteration.md           # Plan work for portfolio iteration
        └── check-learning-outcomes.md  # Map work to learning outcomes
```

---

## Implementation Steps

### Step 1: Create folder structure

Create all directories. ~15 directories total.

### Step 2: Write CLAUDE.md

Rewrite the empty CLAUDE.md with full course context:

* Course overview (program, semester, tech stack, methodology)
* Learning outcomes summary (placeholder to be filled after extraction)
* Assessment structure overview
* Project repos section (circus-train-challenge now, new repos TBD)
* Code standards reference (OOP, SOLID, layered architecture, C# conventions, DB design, Git)
* Portfolio guidance summary
* DOT framework overview
* Knowledge base structure guide
* Instructions for how Claude should help this student

### Step 3: Create 7 slash command files in `.claude/commands/`

Each command reads CLAUDE.md + relevant knowledge base files and accepts $ARGUMENTS:

| Command                      | Purpose                                                                        |
| ---------------------------- | ------------------------------------------------------------------------------ |
| `/help-assignment`         | Break down assignment requirements, map to learning outcomes, suggest approach |
| `/review-portfolio`        | Review portfolio against assessment criteria, identify LO gaps                 |
| `/review-code`             | Code review against SDE standards (SOLID, layered arch, C# conventions)        |
| `/explain-concept`         | Explain course concepts with C#/ASP.NET examples                               |
| `/help-research`           | Help write research docs using DOT framework                                   |
| `/plan-iteration`          | Plan work for a portfolio review iteration                                     |
| `/check-learning-outcomes` | Scan project repos and map work to learning outcomes                           |

### Step 4: Create Priority 1 template files (5 files)

These have custom templates with specific headings for their content type:

1. `course-info/assessment.md` - rubric tables, criteria sections
2. `learning-outcomes/overview.md` - per-LO structured sections
3. `course-info/overview.md` - course structure sections
4. `course-info/individual-project.md` - deliverables, requirements sections
5. `portfolio/portfolio-manual.md` - portfolio format, requirements sections

### Step 5: Create all remaining template files

Universal template with: Source metadata, Summary placeholder, Content section (with copy-paste instructions), Key Takeaways, Related Files.

### Step 6: Update CLAUDE.md with extraction priority guide

Add a section telling the user which files to fill first and why.

---

## Content Extraction Priority (for the user)

### Priority 1 - Extract ASAP (enables the whole system)

1. `course-info/assessment.md` - defines success criteria
2. `learning-outcomes/overview.md` - foundation for everything
3. `course-info/overview.md` - course structure/expectations
4. `course-info/individual-project.md` - primary assessment vehicle
5. `portfolio/portfolio-manual.md` - how to build the portfolio

### Priority 2 - Extract in first 2 weeks

6. `course-info/group-project.md`
7. `portfolio/creating-a-portfolio.md`
8. `portfolio/review-iterations.md`
9. `skills/professional/dot-framework.md`
10. `skills/professional/research-document-template.md`

### Priority 3 - Extract as topics come up in class

11-20. Core technical resources (SOLID, layered arch, OOP, requirements, unit testing, ASP.NET, DI)

### Priority 4 - Extract when relevant

21+. Remaining files as needed throughout semester

---

## Files to Create/Modify

* **Modify:** `CLAUDE.md` (rewrite from empty)
* **Create:** ~55 markdown template files across the folder structure
* **Create:** 7 slash command files in `.claude/commands/`
* **Total:** ~63 files
