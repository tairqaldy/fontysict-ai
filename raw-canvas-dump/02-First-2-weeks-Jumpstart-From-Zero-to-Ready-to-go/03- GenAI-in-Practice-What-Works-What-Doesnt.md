# GenAI in Practice - What Works, What Doesn't

## GenAI in Practice: What Works, What Doesn't

Hands-on skills for effective AI-assisted software development

Start with the page [Generative AI &amp; The Fontys ICT AI Manifest](https://fhict.instructure.com/courses/15759/pages/generative-ai-and-the-fontys-ict-ai-manifest "Generative AI &amp; The Fontys ICT AI Manifest")

Now that you understand the manifesto, let's get hands-on. This workshop focuses on practical skills: how to prompt effectively, when AI shines, when it fails spectacularly, and how to integrate AI into your S2 workflow without losing your soul as a developer.

🎯 Workshop Goals

* Master effective prompting techniques for software development
* Identify AI strengths and critical weaknesses
* Practice AI-assisted analysis, design, and coding workflows
* Build your personal AI toolkit and usage patterns

## Part 1: The Art of Prompting (30 minutes)

Prompt Engineering Fundamentals

#### The CLEAR Framework

* **Concise** → keep it short and sharp, no fluff.
* **Logical** → structure the prompt so the AI can follow a coherent flow.
* **Explicit** → tell it exactly what you expect (format, scope, tone).
* **Adaptive** → leave room for context changes, customization, or constraints.
* **Reflective** → review outputs, tweak prompts, iterate.

### Hands-on Exercise: Prompt Battles

#### 🥊 Round 1: Requirements Analysis

**Scenario:** You're building a student club management system

**Bad Prompt:**

"Write requirements for a club app"

**Better Prompt:**

I'm a software engineering student building a web application for managing student clubs at a university. Context: 200+ active clubs, 5000+ students, clubs need to manage memberships, events, and budgets. Create functional requirements focusing on: - Member registration and management - Event scheduling and attendance tracking - Basic financial tracking Format as user stories with acceptance criteria. Prioritize by MoSCoW method. Example format: As a [role], I want [functionality] so that [benefit] Acceptance criteria: [specific conditions]

**Your Turn:** Try both prompts with your chosen AI tool. Compare the results.

#### 🥊 Round 2: Code Generation

**Challenge:** Get AI to generate a C# class for user authentication

**Your Task:**

1. Write a basic prompt
2. Improve it using the CLEAR framework
3. Test both versions
4. Document what made the difference

## Part 2: AI Strengths - Where It Shines ✨ (25 minutes)

### 🟢 Green Zone: AI Excels Here

#### 1. Boilerplate & Scaffolding

* Controller templates
* Repository patterns
* Unit test structures
* Database migration scripts

**Try this:** "Generate a C# repository pattern for a User entity with CRUD operations using Entity Framework"

#### 2. Code Explanation & Learning

* Breaking down complex algorithms
* Explaining design patterns
* Code review and suggestions
* Refactoring recommendations

**Try this:** Paste some complex code and ask: "Explain this code like I'm a junior developer. What design patterns are used and why?"

#### 3. Alternative Approaches

* Comparing different solutions
* Exploring architectural options
* Suggesting improvements
* Finding edge cases

**Try this:** "I'm implementing authentication. Compare JWT tokens vs session-based auth for my ASP.NET Core app. Include security and scalability considerations."

### Practical Exercise: AI as Your Pair Programming Partner

**Pick one:**

* Generate a user registration controller
* Create unit tests for a calculator class
* Design a database schema for your Individual Project

**Document:** What worked well? What needed your intervention?

## Part 3: AI Failures - Danger Zones ⚠️ (25 minutes)

### 🔴 Red Zone: Where AI Struggles

#### 1. Business Logic & Domain Knowledge

**Problem:** AI doesn't understand your specific business rules

**Example:** "Calculate student grade based on university policies"

**Why it fails:** AI invents policies that don't exist

**Solution:** Provide detailed context and validate everything

#### 2. Security Implementation

**Problem:** AI often suggests outdated or insecure practices

**Example:** May suggest MD5 hashing or SQL concatenation

**Why it fails:** Training data includes old, insecure code

**Solution:** Always validate security code with current best practices

#### 3. Integration & Environment-Specific Issues

**Problem:** AI doesn't know your specific setup

**Example:** Connection strings, deployment configurations

**Why it fails:** No context about your environment

**Solution:** Provide detailed environment context

### Failure Mode Exercise: Spot the Mistakes

Ask AI to generate code for these scenarios and identify the problems:

1. "Create a password hashing function in C#"
2. "Write SQL to delete user data for GDPR compliance"
3. "Generate error handling for a web API"

**Debrief:** What mistakes did you find? How would you fix them?

## Part 4: Building Your AI Workflow (30 minutes)

### The Professional AI-Assisted Development Process

#### Stage 1: Analysis & Planning

1. **Brainstorm with AI:** Generate ideas and explore options
2. **Structure requirements:** Use AI to organize and categorize
3. **Reality check:** You validate feasibility and priorities

#### Stage 2: Design & Architecture

1. **Explore patterns:** Ask AI about design options
2. **Generate diagrams:** Use AI for documentation support
3. **Validate choices:** You ensure it fits your constraints

#### Stage 3: Implementation

1. **Generate scaffolding:** Let AI create boilerplate
2. **Code review loop:** You write logic, AI suggests improvements
3. **Test and debug:** Use AI to help understand errors

### Final Challenge: The Integration Test

**Work in pairs. Pick a small feature from your Individual Project:**

1. **Phase 1:** Use AI to help analyze requirements (15 min)
2. **Phase 2:** Get AI assistance with design decisions (15 min)
3. **Phase 3:** Generate some initial code with AI (15 min)
4. **Phase 4:** Review, test, and refine without AI (15 min)

**Document your experience:**

* Where did AI add real value?
* Where did you have to step in and correct course?
* What would you do differently next time?

Resources & Next Steps

### Recommended Reading

* [GitHub Copilot Documentation**Links to an external site.**](https://docs.github.com/en/copilot/using-github-copilot/getting-started-with-github-copilot)
* [OpenAI Prompt Engineering Guide**Links to an external site.**](https://platform.openai.com/docs/guides/prompt-engineering)
* Search for: "AI-assisted software development best practices 2024"

### Apply This in Your S2 Projects

* **Individual Project:** Start documenting your AI usage from day one
* **Group Project:** Establish team AI usage guidelines
* **Portfolio:** Include reflection on AI-assisted learning
* **Next week:** Try one new AI tool or technique

**💡 Final Thought:** AI doesn't make you less of a programmer - it makes you a programmer who can leverage powerful tools responsibly. The future belongs to developers who understand both the technology AND their own thinking.
