# Product Requirements – FontysICT-AI Knowledge Base (Second Semester Canvas Contents)

## 1. Purpose

Create a **local, AI-ready knowledge base** for the second-semester Software Design & Engineering course at Fontys ICT, by transforming a raw Canvas export (markdown, PDFs, images) into a clean, linked markdown corpus that AI agents can reliably use to support students.

## 2. Primary Users

- **AI agents** (e.g. `/check-learning-outcomes`, `/review-code`, `/plan-iteration`, `/help-assignment`) running against this repo.
- **Students** using those agents to understand learning outcomes, assignments, workshops, and assessment.
- **Teachers/semester coordinators** maintaining course content and agent behavior.

## 3. High-Level Requirements

1. **Canonical content source**
   - All relevant Canvas pages (learning outcomes, portfolio, professional skills, software-development skills, resources, extra challenges) are represented as **completed markdown files** under a clear directory structure (e.g. `learning-outcomes/`, `course-info/`, `portfolio/`, `resources/`, `skills/`, `extra/`).
   - Each content file:
     - Has a standard header (`Source`, `Last updated`, `Status: complete`).
     - Has all Canvas boilerplate removed (submission widgets, duplicated headings, etc.).
     - Uses **relative links** to other files in this repo (no bare Canvas URLs where a local file exists).

2. **Media organization**
   - All referenced images/GIFs are copied from `raw-canvas-dump/` into predictable `images/` folders next to their markdown domains:
     - `portfolio/images/`
     - `resources/**/images/`
     - `skills/**/images/`
     - `extra/images/`
   - Markdown image paths use short, stable filenames (hash-based or semantic) within these folders.
   - `raw-canvas-dump/` remains an untouched archive.

3. **Key reference documents**
   - `CLAUDE.md` acts as the **master agent brief**, containing:
     - The 6 learning outcomes and short definitions.
     - Rubric scale (0/1/2/4/5: Undefined, Orienting, Beginning, Proficient, Advanced).
     - Assessment model (USGO scale, guarantees, committee timing).
     - Quick reference mapping common questions → relevant files.
   - `learning-outcomes/detailed-criteria.md` holds **full LO/rubric clarifications**.
   - `course-info/assessment.md` and `portfolio/review-iterations.md` define:
     - Assessment structure and portfolio expectations.
     - Concrete dates for first review, iterations 1–3, final delivery, final interview, committee week.

4. **Slash-command compatibility**

Ensure `./.claude/commands/*.md` can:
   - Resolve file paths for:
     - Learning outcomes overview and detailed criteria.
     - Portfolio manual, creation guide, iteration pages, review-iterations index.
     - Key skills and resources pages (SOLID, testing, architecture, research, documentation).
   - Provide enough context/examples so commands like `/check-learning-outcomes`, `/review-code`, `/plan-iteration`, `/help-research` can:
     - Map work to LOs.
     - Suggest relevant standards and patterns (e.g. layered architecture, SOLID).
     - Use correct iteration dates and expectations.

5. **Agent behavior expectations**

AI agents using this repo should be able to:
   - Explain each learning outcome, how to demonstrate it, and which artifacts count as evidence.
   - Help students plan iterations with correct dates and expectations.
   - Review code against the semester’s standards (layered architecture, SOLID, testing, DI, state management).
   - Suggest relevant workshops/resources for a given technical or professional skill question.

## 4. Non-Goals

- This project is **not** the live source of truth for Canvas; it mirrors Canvas into an AI-friendly format.
- It does not implement runtime code (no backend/frontend app); it is a **content repository**.
- It is not responsible for grading or storing student work; only for **supporting learning and assessment preparation**.

