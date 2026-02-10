# Unit Testing Practice

> Source: Canvas > Software Development Skills > Implementation (combines Business Logic Testing + Effective Unit Tests)
> Last updated: 2026-02-10
> Status: complete

# 🧪 Unit Testing Mastery

From isolating business logic to writing effective, maintainable tests

This guide combines two essential aspects of unit testing: **isolating business logic** (testing without database dependencies) and **writing effective tests** (avoiding the pitfalls that make tests brittle and unmaintainable).

---

## Part 1: Business Logic Testing in Isolation

**⚠️ The Testing Trap:** Testing business logic with real databases is slow, fragile, and creates false dependencies. When your unit tests require database setup, you're not testing in isolation - you're testing the entire system.

**🎯 Goal:** Master the art of testing business logic in complete isolation using dependency injection and mocking.

### Why Multi-Layered Architecture Matters

**The Power of Decoupling**

This semester, we're developing websites based on multi-layered architecture. The key advantage? **Decoupling between layers** - presentation, business logic, and data access layers operate independently.

* **Business Logic Layer:** Core rules, calculations, and decision-making logic
* **Data Access Layer:** Database operations, external API calls, and persistence
* **Presentation Layer:** User interface, input validation, and display logic

**💡 Testing Benefits:** When layers are properly decoupled, you can test business logic without database setup, external API calls, or UI components. This makes tests faster, more reliable, and focused on what matters - your business rules.

### Prerequisites for Business Logic Testing

**📋 Essential Knowledge:**

* **Unit Testing Fundamentals:** Understanding of test structure, assertions, and test lifecycle
* **Dependency Injection:** Must understand DI concepts - [Review DI Workshop](dependency-injection-aspnet.md)
* **Interface Design:** Creating and implementing interfaces for abstraction
* **SOLID Principles:** Especially Dependency Inversion and Single Responsibility

### Step-by-Step Challenge: Business Logic Testing

**📝 Step 1: Code Analysis & Architecture Review**

Download and analyze the provided codebase. Understanding the current architecture is crucial for effective testing.

**🔍 Critical Analysis Questions:**

* **Functionality:** What does the code do? What's the business domain?
* **Structure:** How is the code organized? Which layers can you identify?
* **Strengths:** What architectural decisions are working well?
* **Weaknesses:** What makes testing difficult? Where are the tight couplings?
* **Dependencies:** Which classes depend on external resources (database, APIs)?

**🎯 Step 2: Test Case Design**

Design comprehensive unit tests for each method in the GameService. Focus on **business logic**, not data access.

**📋 Test Planning Framework:**

* **Happy Path:** What should happen when everything works correctly?
* **Edge Cases:** What happens with boundary values or unusual inputs?
* **Error Conditions:** How should the service handle invalid data or failures?
* **Business Rules:** What domain-specific rules need testing?

**🎭 Step 3: Manual Mock Creation**

Create a custom mock implementation of `IGameRepository` to replace the real repository in tests.

**🔧 Mock Implementation Strategy:**

* **Predictable Data:** Return consistent, known test data
* **Behavior Verification:** Track which methods were called and with what parameters
* **Failure Simulation:** Allow testing of error scenarios
* **No Side Effects:** Avoid any real database operations

**🧪 Step 4: Test Implementation**

Implement the actual unit tests using your custom mock. Focus on testing **business logic behavior**, not data persistence.

**Test Structure Example (Arrange-Act-Assert):**

```csharp
[Test]
public async Task CalculateScore_ReturnsCorrectScore_WhenGameIsComplete()
{
    // Arrange
    var mockRepository = new GameRepositoryMock();
    var gameService = new GameService(mockRepository);

    // Act
    var result = await gameService.CalculateScore(gameId);

    // Assert
    Assert.That(result, Is.EqualTo(expectedScore));
}
```

**🔬 Step 5: Professional Mocking with Moq**

Explore professional mocking frameworks like **Moq** for more flexible and maintainable test code.

**Moq Example:**

```csharp
[Test]
public async Task GetGame_ReturnsGame_WhenGameExists()
{
    var mockRepository = new Mock<IGameRepository>();
    var expectedGame = new Game { Id = 1, Name = "Test Game" };
    mockRepository.Setup(x => x.GetGameAsync(1)).ReturnsAsync(expectedGame);
    var service = new GameService(mockRepository.Object);

    var result = await service.GetGame(1);

    Assert.That(result.Name, Is.EqualTo("Test Game"));
    mockRepository.Verify(x => x.GetGameAsync(1), Times.Once);
}
```

**🔗 Learn More:** Check out the [Moq GitHub repository](https://github.com/devlooped/moq) for comprehensive documentation and examples.

---

## Part 2: Writing Effective Unit Tests

**⚠️ The Testing Paradox:** Writing a unit test is easy. Writing an *effective* unit test is an art form. You can have 100% code coverage and still have brittle, unmaintainable tests that give false confidence.

**🎯 Goal:** Transform from someone who writes tests to someone who writes *effective* tests. Learn the subtle art of test design, maintainability, and the difference between testing implementation details versus testing behavior.

### The Four Horsemen of Testing Apocalypse

**☠️ Death by Poor Coverage**

Your tests look comprehensive but miss the edge cases that matter. They test the happy path but ignore the scenarios that break in production.

**🔧 Death by Complexity**

Tests are harder to read than the code they're testing. They ignore OO principles, have massive setup methods, and nobody wants to touch them.

**💔 Death by Fragility**

Tests fail when you refactor perfectly good code. They're testing *how* something works rather than *what* it should do.

**🕳️ Death by Untestability**

Your code is so tightly coupled that writing tests requires spinning up entire databases, web servers, and external APIs.

### Prerequisites for Effective Testing

**📋 Essential Skills:**

* **Basic Unit Testing:** You know how to write unit tests ([Unit Testing](../../resources/implementation/unit-testing.md))
* **Layered Architecture:** You can apply layered architecture in your software design ([Layered Architecture](../../resources/design/layered-architecture.md))
* **Testing Framework:** MSTest, NUnit, or xUnit

### Best Practices for Effective Tests

**1. Single Assert Principle**

Avoid multiple asserts in one test when they test different concerns. If one fails, you lose context about the others.

**2. Test Behavior, Not Implementation**

Tests should verify *what* the code does (outcomes), not *how* it does it. This allows refactoring without breaking tests.

**3. Meaningful Test Names**

Use names that describe the scenario and expected result: `CalculateScore_ReturnsCorrectScore_WhenGameIsComplete`

**4. Arrange-Act-Assert Structure**

Keep the three phases clear and separate. No logic in Assert beyond checking the result.

**5. Avoid Test Duplication**

Extract common setup into helper methods or test fixtures, but keep tests independent.

**6. Test Void Methods via Side Effects**

When testing methods that return void, test the side effects (e.g., repository was called, state changed).

**7. Use Collection Assertions**

For methods returning collections, use framework collection assertions rather than manual iteration.

**Resources:**

* [Microsoft's Unit Testing Best Practices](https://learn.microsoft.com/en-us/dotnet/core/testing/unit-testing-best-practices#avoid-multiple-acts)

### The Investment Platform Challenge

**📊 Your Mission: Refactor a Real Testing Nightmare**

You've inherited an investment platform with existing unit tests that exhibit classic problems. Your job is to transform them into professional-grade tests.

**Phase 1: Refactor Existing Tests**

* Identify assertion problems - why are certain asserts sub-optimal?
* Find multiple assert violations - which tests violate the single assert principle?
* Propose solutions - how can you improve maintainability while keeping coverage?

**Phase 2: Advanced Testing Patterns**

* **The Void Method Challenge:** How do you test `AddInvestment()` when it returns void? Test the side effects, not the return value.
* **The Collections Challenge:** How do you effectively test `GetUpcomingProjectPayments()` which returns ordered arrays? Use framework collection assertions.

---

## 🎯 Learning Outcome Connection

**LO4: Managing - Testing & Quality**

This workshop directly supports your ability to:

* **Define and Execute Tests:** Create comprehensive unit tests for business logic
* **Ensure Code Quality:** Use testing to verify functionality and prevent regressions
* **Iterative Improvement:** Continuously improve code quality through testing
* **Professional Standards:** Apply industry-standard testing practices and frameworks

## 🚀 Next Steps

**🎯 Apply to Your Project:**

1. **Review Architecture:** Identify business logic in your individual project
2. **Create Tests:** Implement unit tests for your service layer
3. **Use Mocking:** Apply mocking strategies to isolate business logic
4. **Discuss with Teachers:** Share your testing approach and get feedback

**⚠️ Teacher Review:** Before implementing tests in your project, discuss your testing strategy with your teachers. They can provide valuable feedback on your approach and help you identify the most important business logic to test.

*The best unit tests are small, fast, and focused. If your test needs a database, it's not a unit test - it's an integration test. Master the art of testing business logic in isolation, and you'll write better, more maintainable code. The goal isn't to write more tests - it's to write tests that give you confidence to refactor, extend, and maintain your code without fear.*
