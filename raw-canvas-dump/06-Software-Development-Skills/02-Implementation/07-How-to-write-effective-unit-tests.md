# How to write effective unit tests?

# 🎯 Effective Unit Testing Mastery

From simple tests to maintainable, robust test suites

**⚠️ The Testing Paradox:** Writing a unit test is easy. Writing an *effective* unit test is an art form. You can have 100% code coverage and still have brittle, unmaintainable tests that give false confidence. The difference between good and great developers isn't just writing tests - it's writing tests that actually improve code quality and catch real problems.

**🎯 Workshop Goal:** Transform from someone who writes tests to someone who writes *effective* tests. Learn the subtle art of test design, maintainability, and the difference between testing implementation details versus testing behavior.

![1770717644526](image/07-How-to-write-effective-unit-tests/1770717644526.png)

## 💭 The Real-World Testing Challenge

**🏢 The Production Reality Check**

Picture this: You've deployed your software and have paying users relying on it daily. Your team has grown, the original developers have moved on, and you're now responsible for maintaining and extending a system that generates revenue. Every bug costs money, every downtime loses customers, and every new feature risks breaking existing functionality.

In this environment, unit tests aren't just nice-to-have - they're your safety net, your documentation, and your confidence booster all rolled into one. But here's the catch:  **ineffective tests are worse than no tests at all** .

**⚠️ The Testing Trap:** Bad tests give false confidence, take time to maintain, and can actually make refactoring *harder* rather than easier. They become a burden instead of a benefit.

## 🚨 The Four Horsemen of Testing Apocalypse

**☠️ Death by Poor Coverage**

Your tests look comprehensive but miss the edge cases that matter. They test the happy path but ignore the scenarios that break in production.

**Symptoms:** "But it worked in the demo!" - Tests pass but users find bugs immediately.

**🔧 Death by Complexity**

Tests are harder to read than the code they're testing. They ignore OO principles, have massive setup methods, and nobody wants to touch them.

**Symptoms:** "Just skip the tests for now, we'll fix them later" - Spoiler: They never get fixed.

**💔 Death by Fragility**

Tests fail when you refactor perfectly good code. They're testing *how* something works rather than *what* it should do.

**Symptoms:** "The refactoring broke all the tests but the code still works" - Tests become barriers to improvement.

**🕳️ Death by Untestability**

Your code is so tightly coupled that writing tests requires spinning up entire databases, web servers, and external APIs.

**Symptoms:** "We can't test this because it depends on everything" - Tests become integration nightmares.

## 🛠️ Prerequisites & Setup

 **📋 Essential Skills:** * **Basic Unit Testing:** [You know how to write unit tests](https://fhict.instructure.com/courses/15759/pages/automated-unit-testing)

* **Layered Architecture:** [You can apply layered architecture in your software design](https://fhict.instructure.com/courses/15759/pages/layered-architecture)
* **Testing Framework:** This workshop uses [MSTest Framework**Links to an external site.**](https://learn.microsoft.com/en-us/dotnet/core/testing/unit-testing-mstest-intro)

 **📁 Workshop Resources:** * **Practice Application:** [FundingPlatform.zip](https://fhict.instructure.com/courses/15759/files/2576931?verifier=txS30S6OZJpF9vruNMTIWI0qMpS5p9jRdHv6g4er&wrap=1) - Investment platform with existing (flawed) tests

* **Testing Best Practices:** [Microsoft&#39;s Unit Testing Best Practices**Links to an external site.**](https://learn.microsoft.com/en-us/dotnet/core/testing/unit-testing-best-practices#avoid-multiple-acts)

## 💬 Discussion & Questions

Questions about testing strategies, maintainability, or best practices?

[💬 Join Testing Discussion](https://fhict.instructure.com/courses/15759/discussion_topics/94074)

## 🎭 The Investment Platform Challenge

**📊 Your Mission: Refactor a Real Testing Nightmare**

You've inherited an investment platform with existing unit tests that exhibit all the classic problems of ineffective testing. The application has three core features:

**💰 Project Management:** Create and view funding projects

**📅 Payment Tracking:** View upcoming project payments

**💸 Investment System:** Invest in projects

**🎯 The Learning Twist:** The existing tests have good coverage but suffer from all the maintainability issues we discussed. Your job is to transform them into professional-grade tests.

## 🔧 Two-Phase Transformation

**🛠️ Phase 1: Refactor Existing Tests**

Start by downloading the investment platform and analyzing the existing codebase. You'll find unit tests for `AddProject()` and `GetProject()` that demonstrate classic testing antipatterns.

 **🔍 Your Detective Work:** 1. **Pair Up:** Team up with another student for collaborative analysis

1. **Identify Assertion Problems:** Why are the asserts in `AddProject_ValidData_Success()` sub-optimal?
2. **Find Multiple Assert Violations:** Which unhappy-flow tests violate the [single assert principle**Links to an external site.**](https://learn.microsoft.com/en-us/dotnet/core/testing/unit-testing-best-practices#avoid-multiple-acts)?
3. **Propose Solutions:** How can you improve maintainability while keeping coverage?

**💡 Pro Tip:** Look for code duplication in test setup. This is often the first sign of tests that will become maintenance nightmares.

**🎯 Phase 2: Advanced Testing Patterns**

Now tackle the more sophisticated testing challenges that separate beginners from professionals.

 **🎪 The Void Method Challenge:** How do you test `AddInvestment()` when it returns void? This is where many developers give up, but professionals know the secret:  **test the side effects, not the return value** .

 **📊 The Collections Challenge:** How do you effectively test `GetUpcomingProjectPayments()` which returns ordered arrays? Hint: Testing frameworks have special collection assertions for a reason.

**🎯 Deliverable:** Choose your best implementation to present to a teacher for feedback. This isn't just about getting the right answer - it's about articulating your testing philosophy.

## 🎯 Learning Outcome Connection

**LO4: Managing - Testing & Quality Improvement**

This workshop directly demonstrates your mastery of:

* **Advanced Testing Techniques:** Moving beyond basic unit tests to professional-grade testing
* **Quality Improvement:** Using testing to continuously improve code maintainability
* **Technical Decision-Making:** Choosing appropriate testing strategies based on code structure
* **Collaborative Problem-Solving:** Working in pairs to solve complex testing challenges

## 🚀 Next Steps & Future Learning

 **🔄 Immediate Actions:** 1. **Process Feedback:** Apply teacher feedback to refine your testing approach

1. **Optional Practice:** Complete the remaining unit tests marked in `#region optional`
2. **Reflect on Strategy:** Document your testing philosophy for your portfolio

**🔮 Looking Ahead:** Next semester, you'll dive deeper into advanced testing concepts including mocking frameworks, integration testing, and test-driven development. The foundations you build here will be crucial for that journey.

*🎯 Testing Wisdom: The goal isn't to write more tests - it's to write tests that give you confidence to refactor, extend, and maintain your code without fear. When your tests become your safety net rather than your burden, you've mastered the art of effective testing.*
