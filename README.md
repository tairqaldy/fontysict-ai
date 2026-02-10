# Fontys ICT S2 – Software Design & Engineering Knowledge Base

An AI-ready knowledge base for the second-semester Software Design & Engineering course at Fontys ICT. Course materials, assessment criteria, and learning resources are organized as markdown for reliable use by AI agents and students.

## For Students

### What is this?

This repository contains course content from Canvas (learning outcomes, portfolio guidance, workshops, resources) in a structured format so AI assistants can reliably answer questions about the S2 SDE course.

### How to use it with Cursor

1. **Open this repo in Cursor** – Use it as a workspace or add it to your workspace alongside your project repos.
2. **Use slash commands** – Type `/` in the Cursor chat to see available commands.
3. **Ask questions** – The AI uses this knowledge base when helping with S2 SDE topics.

### Slash commands

| Command | Use it to |
|--------|------------|
| `/check-learning-outcomes` | Analyse your work against the 6 learning outcomes and spot gaps |
| `/explain-concept` | Get a clear explanation of a concept (SOLID, DI, testing, etc.) |
| `/help-assignment` | Break down an assignment and link it to learning outcomes |
| `/help-research` | Structure a research document with the DOT framework |
| `/plan-iteration` | Plan work for a portfolio review iteration |
| `/review-code` | Review code against SDE standards (SOLID, layered architecture, etc.) |
| `/review-portfolio` | Get feedback on your portfolio and evidence |

### Key documents

| Topic | File |
|-------|------|
| Learning outcomes (full) | [learning-outcomes/detailed-criteria.md](learning-outcomes/detailed-criteria.md) |
| Assessment & dates | [portfolio/review-iterations.md](portfolio/review-iterations.md) |
| Portfolio creation | [portfolio/creating-a-portfolio.md](portfolio/creating-a-portfolio.md) |
| Workshop schedule | [course-info/workshop-schedule.md](course-info/workshop-schedule.md) |
| Individual project | [course-info/individual-project.md](course-info/individual-project.md) |
| Group project | [course-info/group-project.md](course-info/group-project.md) |

### IDE integrations

This repo includes config for several AI coding assistants:

| IDE / Tool | Config | Notes |
|------------|--------|------|
| **Cursor** | `.cursor/rules/`, `.cursor/commands/` | Slash commands + rules |
| **GitHub Copilot** | `.github/copilot-instructions.md` | Repo-wide instructions |
| **Windsurf** | `.windsurfrules`, `.windsurf/rules/` | Workspace rules |
| **Continue.dev** | `.continue/rules/` | Local rules |
| **Codeium** | `.codeium/project-instructions.md` | Project instructions |
| **Codex** | `.codex/AGENTS.md`, `AGENTS.md` | Agent instructions |

Open this repo in any of these tools and the AI will use the knowledge base. Cursor also provides slash commands (see above).

### Recommended setup

- Keep this repo in the same parent folder as your project repos (e.g. `fontys-projects/`).
- Open a workspace that includes both this repo and your project repos so the AI can use both.
- For project-specific help, mention which project you’re working on.

## Structure

```
├── CLAUDE.md              # Master agent brief (LOs, rubric, dates, standards)
├── learning-outcomes/     # LO definitions and criteria
├── course-info/           # Assessment, projects, workshop schedule
├── portfolio/             # Portfolio manual, iterations, reviews
├── resources/             # Theory (analysis, design, implementation, manage & control)
├── skills/                # Professional & software-development skills
│   ├── professional/     # Research, feedback, planning, documentation, DOT, etc.
│   └── software-development/
│       ├── analysis/     # Requirements, use cases, conceptual models
│       ├── design/      # Architecture, SOLID, DB design, wireframes
│       ├── implementation/  # OOP, HTML/CSS, ASP.NET, testing, DI, statefulness
│       └── manage-and-control/  # Debugging, deployment
├── jumpstart/             # First 2 weeks material
├── extra/                 # Extra challenges, AI manifest, Student+
├── .cursor/               # Cursor IDE (rules, slash commands)
├── .github/               # GitHub Copilot (copilot-instructions.md)
├── .windsurf/             # Windsurf IDE (rules)
├── .continue/             # Continue.dev (rules)
├── .codeium/              # Codeium (project instructions)
├── .codex/                # Codex (AGENTS.md)
├── AGENTS.md              # Agent instructions (Copilot, Codex, etc.)
└── raw-canvas-dump/       # Original Canvas export (read-only)
```

## For Teachers & Maintainers

- **CLAUDE.md** is the main agent brief; update it when course structure or dates change.
- **prd.md** documents the knowledge base requirements.
- **raw-canvas-dump/** is not modified; it is the source archive.
- After Canvas updates, re-export and re-run any extraction scripts to keep content in sync.

## License & Attribution

Course content originates from Fontys ICT. This repository is a local mirror for AI-assisted learning support.
