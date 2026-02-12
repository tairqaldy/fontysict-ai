# Product Requirements – Fontys ICT AI Learning Partner Platform

## 1. Purpose

Build a **university-supported web platform** that empowers Fontys Hogeschool ICT students to accelerate their educational and development journeys through an **AI learning partner** – not a vibecoding tool, but a pedagogically aligned assistant that references course context, learning outcomes, and student projects to support understanding, planning, and reflective practice.

**Positioning:** This is a **regulatory, learning-focused** initiative aligned with Fontys ICT’s AI Manifest and institutional goals. The platform treats AI as a learning partner that helps students grasp concepts, plan work, and validate their understanding – NOT as a shortcut to production.

---

## 2. Primary Users

| User                              | Goals                                                                                                                                                      |
| --------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Students**                | Ask questions, plan iterations, get code feedback, explore concepts, and prepare for portfolio reviews with AI that understands their course and projects. |
| **Teachers / Coordinators** | Curate course context, monitor usage patterns, and ensure AI guidance aligns with learning outcomes and assessment criteria.                               |
| **University**              | Offer a branded, compliant, and pedagogically sound AI environment that supports Fontys’ Responsible AI approach.                                         |

---

## 3. High-Level Requirements

### 3.1 GitHub Integration

- **User project referencing**
  - Students can connect GitHub accounts and **select which repos** (individual, group, extra projects) the AI agent can read.
  - OAuth 2.0 for secure, scoped access (read-only by default).
  - AI can reference file contents, structure, and commit history when helping with code review, planning, or LO mapping.
- **Repository context**
  - Optional: AI can fetch and index selected repos (or specific branches) for the session.
  - Support for private repos when the student grants access.

### 3.2 Course Context for AI

**Recommendation: Hybrid approach**

| Source                               | Purpose                                                                             | Rationale                                                                                                      |
| ------------------------------------ | ----------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| **GitHub repo (maintainable)** | Course materials, learning outcomes, skills, resources, CLAUDE.md-style agent brief | Version-controlled, editable by teachers, same structure as current `second-semester-canvas-course-contents` |
| **Structured database**        | User profiles, preferences, learning history, analytics, personalization            | Enables “remember me,” progress tracking, and session continuity                                             |

**Option A (recommended):**

- **Primary:** GitHub repo mirrors `second-semester-canvas-course-contents` (or a consolidated Fontys course repo). The platform fetches/ingests markdown on a schedule or on-demand.
- **Why:** Teachers can update content via PRs; single source of truth; no duplicated content.
- **Secondary:** DB stores user progress, conversation summaries, and preferences.

**Option B (alternative):**

- Full DB with imported course content (markdown → structured records).
- **Pros:** Faster queries, rich filtering, analytics.
- **Cons:** Duplication, sync complexity, slower updates by teachers.

**Recommendation:** Option A for course content; DB only for user-specific and operational data.

### 3.3 AI Model Selection & Subscription

- **Free tier**
  - One capable model (e.g., GPT-4o-mini or Claude Haiku) for short questions, quick explanations.
  - Limited context window; suitable for “what is SOLID?” or “explain this error.”
- **Subscription tier**
  - **Better models:** Claude Opus/Sonnet, GPT-4o/GPT-4 for:
    - Code review and implementation planning
    - Longer iterations (e.g., “plan my next 2 weeks”, "assign tasks in a form of Trello to team of 5 for project X for next week")
    - Research and reflection support
  - **Higher limits:** More tokens, longer context, more referenced files.
  - **Tooling:** Multi-file code review, project-level planning.
- **Model choice**
  - Users can pick provider (Claude vs OpenAI) and model within their tier.
  - Implementation: Vercel AI Gateway or equivalent for unified routing and cost control.

### 3.4 Core Interface

- **Chat-first**
  - Conversation as the primary interaction; replies stream in real time.
  - Messages can embed code blocks, file references, and structured suggestions.
- **Split-screen layout (Lovable / 21st.dev inspired)**
  - **Left:** Chat thread.
  - **Right:** Context panel that can show:
    - Code in an embedded editor (Monaco or similar)
    - File tree of referenced repo
    - Diff view for proposed changes
  - Layout responsive: stacked on mobile, side-by-side on desktop.
- **In-web code review**
  - View files and suggested edits in the right panel.
  - Review changes before committing; optional “copy to clipboard” or “apply patch” flows.
  - No automatic commits; student remains in control (aligns with AI Manifest: validation is student responsibility).

### 3.5 Design & Component Philosophy

- **Design first**
  - Define typography, spacing, color tokens, and component library before implementation.
  - Use **21st.dev** or similar for reusable UI (dialogs, inputs, cards, tables).
  - Avoid generic “AI startup” look; aim for a calm, academic, accessible feel.
- **Inspiration**
  - Lovable: split chat/code, clear call-to-actions.
  - Bolt.new: Landing inspo but in Fontys colors.
  - Notion/Cursor: structured navigation, clean editor.
  - Fontys branding: colors, logo, accessibility (WCAG 2.1 AA where feasible). (i think more about deep purple and purple gradients (curated) in white purple and black purple variations)

### 3.6 Personalization & Data Storage

- **Stored per user**
  - Profile (name, program, semester, linked GitHub)
  - Linked repos and last-synced metadata
  - Conversation history (per session or rolling window)
  - Preferences (default model, UI layout, notification settings)
- **Learning analytics (optional)**
  - Usage patterns (topics, models, time of day)
  - Aggregated, anonymized insights for university
  - No grading; only support for improving the platform and pedagogy.

### 3.7 AI as Learning Partner

The system prompt and behavior must reflect:

- **Learning over output:** Focus on understanding, not just completing tasks.
- **Transparency:** Encourage documenting AI usage (per AI Manifest).
- **Validation:** Remind students to verify AI suggestions before applying.
- **LO alignment:** When relevant, tie advice to learning outcomes and rubric levels.
- **Course standards:** Apply SDE standards (SOLID, layered architecture, C# conventions) in code help.

---

## 4. Feature Summary

| Feature              | Free             | Subscription            |
| -------------------- | ---------------- | ----------------------- |
| Chat with AI         | ✓ (basic model) | ✓ (Claude / GPT-4o)    |
| Short questions      | ✓               | ✓                      |
| Code explanations    | ✓               | ✓                      |
| GitHub repo linking  | ✓ (1 repo)      | ✓ (multiple repos)     |
| Code review          | Limited          | Full, multi-file        |
| Iteration planning   | Limited          | Full, longer context    |
| Research / DOT help  | Limited          | Full                    |
| Context window       | ~4K tokens       | ~128K+                  |
| Conversation history | 7 days           | Extended (configurable) |

---

## 5. Technical Considerations

- **Stack (suggested)**

  - Next.js 14+ (App Router), React, TypeScript
  - Vercel AI SDK for streaming, tool use, multi-model
  - Supabase or similar for auth, DB, storage
  - GitHub OAuth for repo access
- **Course content ingestion**

  - Cron or webhook to sync from GitHub repo
  - Markdown → chunks for RAG or context injection
- **Monetization**

  - University-sponsored free tier
  - Optional student subscription for premium models
  - Or full university contract (no student fee)

---

## 6. Non-Goals

- **Not a grading system:** AI does not score or grade work.
- **Not a replacement for Canvas:** Platform complements Canvas; it does not replicate LMS functionality.
- **Not a code generator only:** Primary value is learning support, not “write my code.”
- **No automatic commits:** Students decide when and how to apply changes.

---

## 7. Success Metrics

- Student engagement (sessions per week, questions per session)
- Subjective feedback (NPS, “helped my understanding”)
- Alignment with learning outcomes (qualitative teacher feedback)
- Responsible use (documentation of AI usage in portfolios)

---

## 8. Phased Roadmap (Draft)

| Phase             | Scope                                                                   |
| ----------------- | ----------------------------------------------------------------------- |
| **MVP**     | Auth, chat (1 model), course context from GitHub repo, basic split view |
| **Phase 2** | GitHub integration, multi-repo linking, code editor panel               |
| **Phase 3** | Subscription, model selection, personalization                          |
| **Phase 4** | Analytics, teacher dashboard, university-wide rollout                   |

---

## 9. Open Questions

1. **University sponsorship:** Will Fontys fund infrastructure and premium models for all students, or only a free tier?
2. **Data residency:** Dutch/EU hosting and GDPR compliance requirements?
3. **Canvas integration:** Deep link to assignments, or standalone only?
4. **Access control:** SSO with Fontys credentials (e.g., SURFconext)?
