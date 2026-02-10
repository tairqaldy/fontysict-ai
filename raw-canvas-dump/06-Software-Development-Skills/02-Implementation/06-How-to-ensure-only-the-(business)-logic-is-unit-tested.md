# How to ensure only the (business) logic is unit tested?

# 🧪 Business Logic Testing Mastery

Isolate and test your business logic without database dependencies

**⚠️ The Testing Trap:** Testing business logic with real databases is slow, fragile, and creates false dependencies. When your unit tests require database setup, you're not testing in isolation - you're testing the entire system. This leads to brittle tests that break when infrastructure changes, not when business logic fails.

**🎯 Workshop Goal:** Master the art of testing business logic in complete isolation using dependency injection and mocking. Learn to write fast, reliable unit tests that focus exclusively on your business rules and logic, not on database interactions or external dependencies.

## 🏗️ Why Multi-Layered Architecture Matters

**🎨 The Power of Decoupling**

This semester, we're developing websites based on multi-layered architecture. The key advantage? **Decoupling between layers** - presentation, business logic, and data access layers operate independently.

#### 🎯 Business Logic Layer

Contains your application's core rules, calculations, and decision-making logic

#### 🗄️ Data Access Layer

Handles database operations, external API calls, and persistence

#### 🖥️ Presentation Layer

Manages user interface, input validation, and display logic

**💡 Testing Benefits:** When layers are properly decoupled, you can test business logic without database setup, external API calls, or UI components. This makes tests faster, more reliable, and focused on what matters - your business rules.

## 🛠️ Prerequisites & Setup

 **📋 Essential Knowledge:** * **Unit Testing Fundamentals:** Understanding of test structure, assertions, and test lifecycle

* **Dependency Injection:** Must understand DI concepts - [Review DI Workshop](https://fhict.instructure.com/courses/15759/pages/how-to-leverage-dependency-injection-di-with-asp-dot-net)
* **Interface Design:** Creating and implementing interfaces for abstraction
* **SOLID Principles:** Especially Dependency Inversion and Single Responsibility

 **📁 Exercise Resources:** * **Starting Code:** [MultiLayerExample.zip](https://fhict.instructure.com/courses/15759/files/2576818?verifier=tpJ6uzjL0Ma0ONm3Fy3Il19UwW8OcpzPyITbXyah&wrap=1)

* **Database Setup:** [Game.sql](https://fhict.instructure.com/courses/15759/files/2576901?verifier=WfgEAuLHLU1xjR9vrIQilKa0ZB2K5biG4EQ97v4K&wrap=1) (optional for running the website)
* **Configuration:** Don't forget to edit the connection string in `appsettings.json`

## 💬 Discussion & Questions

Questions about testing business logic or mocking strategies?

[💬 Join Testing Discussion](https://fhict.instructure.com/courses/15759/discussion_topics/94069)

## 🔍 Step-by-Step Challenge

**⚠️ Important:** This workshop is divided into progressive steps. **Ask for feedback during each step** to ensure you're on the right track and learning effectively.

**📝 Step 1: Code Analysis & Architecture Review**

Download and analyze the provided codebase. Understanding the current architecture is crucial for effective testing.

 **🔍 Critical Analysis Questions:** * **Functionality:** What does the code do? What's the business domain?

* **Structure:** How is the code organized? Which layers can you identify?
* **Strengths:** What architectural decisions are working well?
* **Weaknesses:** What makes testing difficult? Where are the tight couplings?
* **Dependencies:** Which classes depend on external resources (database, APIs)?

**🎯 Step 2: Test Case Design**

Design comprehensive unit tests for each method in the GameService. Focus on  **business logic** , not data access.

 **📋 Test Planning Framework:** * **Happy Path:** What should happen when everything works correctly?

* **Edge Cases:** What happens with boundary values or unusual inputs?
* **Error Conditions:** How should the service handle invalid data or failures?
* **Business Rules:** What domain-specific rules need testing?

**🎭 Step 3: Manual Mock Creation**

Create a custom mock implementation of `IGameRepository` to replace the real repository in tests.

 **🔧 Mock Implementation Strategy:** * **Predictable Data:** Return consistent, known test data

* **Behavior Verification:** Track which methods were called and with what parameters
* **Failure Simulation:** Allow testing of error scenarios
* **No Side Effects:** Avoid any real database operations

Example Mock Structure:

`
                    public class GameRepositoryMock : IGameRepository
                    {
                    private readonly List`<Game>` _games = new();

    public Task`<Game>` GetGameAsync(int id)
                    {
                    var game = _games.FirstOrDefault(g => g.Id == id);
                    return Task.FromResult(game);
                    }

    // Implement other methods...
                    }
                `

**🧪 Step 4: Test Implementation**

Implement the actual unit tests using your custom mock. Focus on testing  **business logic behavior** , not data persistence.

Test Structure Example:

`
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
                `

**🔬 Step 5: Professional Mocking with Moq**

Explore professional mocking frameworks like **Moq** for more flexible and maintainable test code.

 **📚 Moq Advantages:** * **Less Code:** Auto-generates mock implementations

* **Flexible Setup:** Easy to configure different scenarios
* **Verification:** Built-in verification of method calls
* **Professional Standard:** Industry-standard mocking approach

Moq Example:

`
                    [Test]
                    public async Task GetGame_ReturnsGame_WhenGameExists()
                    {
                    // Arrange
                    var mockRepository = new Mock`<IGameRepository>`();
                    var expectedGame = new Game { Id = 1, Name = "Test Game" };

    mockRepository.Setup(x => x.GetGameAsync(1))
                    .ReturnsAsync(expectedGame);

    var service = new GameService(mockRepository.Object);

    // Act
                    var result = await service.GetGame(1);

    // Assert
                    Assert.That(result.Name, Is.EqualTo("Test Game"));
                    mockRepository.Verify(x => x.GetGameAsync(1), Times.Once);
                    }
                `

**🔗 Learn More:** Check out the [Moq GitHub repository**Links to an external site.**](https://github.com/devlooped/moq) for comprehensive documentation and examples.

## 🎯 Learning Outcome Connection

**LO4: Managing - Testing & Quality**

This workshop directly supports your ability to:

* **Define and Execute Tests:** Create comprehensive unit tests for business logic
* **Ensure Code Quality:** Use testing to verify functionality and prevent regressions
* **Iterative Improvement:** Continuously improve code quality through testing
* **Professional Standards:** Apply industry-standard testing practices and frameworks

## 🚀 Next Steps

 **🎯 Apply to Your Project:** 1. **Review Architecture:** Identify business logic in your individual project

1. **Create Tests:** Implement unit tests for your service layer
2. **Use Mocking:** Apply mocking strategies to isolate business logic
3. **Discuss with Teachers:** Share your testing approach and get feedback

**⚠️ Teacher Review:** Before implementing tests in your project, discuss your testing strategy with your teachers. They can provide valuable feedback on your approach and help you identify the most important business logic to test.

*🧪 Testing Truth: The best unit tests are small, fast, and focused. If your test needs a database, it's not a unit test - it's an integration test. Master the art of testing business logic in isolation, and you'll write better, more maintainable code.*
