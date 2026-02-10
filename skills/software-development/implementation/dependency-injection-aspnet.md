# How to leverage Dependency Injection (DI) with ASP.NET?

> Source: Canvas > Software Development Skills > Implementation
> Last updated: 2026-02-10
> Status: complete

# 🔧 Dependency Injection Mastery

Build loosely coupled, testable, and maintainable applications with ASP.NET Core DI

**⚠️ The Coupling Problem:** Tightly coupled code is the root of most maintenance nightmares. When classes directly instantiate their dependencies, changing one component breaks others. Dependency Injection solves this by inverting control - dependencies are provided from outside, creating flexible, testable, and maintainable applications.

**🎯 Workshop Goal:** Master Dependency Injection patterns and ASP.NET Core's DI container. Learn to design loosely coupled applications that are easy to test, maintain, and extend. Transform tightly coupled code into flexible, professional architecture.

## 🏗️ Understanding Dependency Injection

**❌ Tightly Coupled (The Problem)**

```csharp
public class OrderService
{
    private readonly EmailService _emailService;
    private readonly DatabaseService _databaseService;

    public OrderService()
    {
        _emailService = new EmailService();
        _databaseService = new DatabaseService();
    }
    // Methods that use the services...
}
```

**Problems:** Hard to test, difficult to change implementations, violates SOLID principles

**✅ Loosely Coupled (The Solution)**

```csharp
public class OrderService
{
    private readonly IEmailService _emailService;
    private readonly IDatabaseService _databaseService;

    public OrderService(IEmailService emailService, IDatabaseService databaseService)
    {
        _emailService = emailService ?? throw new ArgumentNullException(nameof(emailService));
        _databaseService = databaseService ?? throw new ArgumentNullException(nameof(databaseService));
    }
    // Methods that use the services...
}
```

**Benefits:** Testable with mocks, flexible implementations, follows SOLID principles

## ⚙️ DI Patterns & Service Lifetimes

**🔧 Injection Types**

#### Constructor Injection (Recommended)

Dependencies injected via constructor. Ensures all required dependencies are available at object creation.

#### Property Injection

Dependencies set via properties. Useful for optional dependencies or framework integration.

#### Method Injection

Dependencies passed as method parameters. Good for contextual dependencies.

**⏰ Service Lifetimes**

| Lifetime    | Scope                        | Use Case                                     |
| ----------- | ---------------------------- | -------------------------------------------- |
| **Transient** | New instance every time      | Lightweight services, stateless operations   |
| **Scoped**    | One instance per request     | Database contexts, request-specific services |
| **Singleton** | One instance per application | Caching, logging, configuration              |

## 🛠️ Prerequisites & Setup

**📋 Essential Knowledge:**

* [SOLID Principles](../design/solid-in-practice.md) - especially Dependency Inversion
* Understanding of interfaces and abstract classes
* Basic knowledge of ASP.NET Core architecture
* Familiarity with unit testing concepts

**📚 Resources:**

* [ASP.NET Core Dependency Injection](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection)

## 🏭 Refactoring Challenge: User Management System

**🎯 The Scenario: Tightly Coupled Mess**

You've inherited a user management system with tight coupling between layers. The IndexModel directly depends on UserService, which directly instantiates UserDB. This creates a chain of dependencies that's hard to test and maintain.

**Current Problems:**

* Hard to unit test - requires real database
* Difficult to change implementations
* Violates Single Responsibility Principle
* No flexibility for different environments

### Phase 1: Dependency Analysis

**🔍 Critical Analysis Questions:**

* **Coupling Issues:** What happens when you want to change the database implementation?
* **Testing Problems:** How would you unit test UserService without a real database?
* **Flexibility:** How would you use different implementations for different environments?
* **SOLID Violations:** Which SOLID principles are being violated?
* **Maintenance:** What's the impact of adding new features or changing existing ones?

**🎯 Design Goals:**

* Decouple layers through interfaces
* Enable unit testing with mocks
* Support multiple implementations
* Follow Dependency Inversion Principle
* Leverage ASP.NET Core DI container

### Phase 2: Interface Design & Abstraction

**🎨 Creating Abstractions**

**Step 1: Define Interfaces**

```csharp
public interface IUserRepository
{
    Task<User> GetUserAsync(int id);
    Task<IEnumerable<User>> GetAllUsersAsync();
    Task<User> CreateUserAsync(User user);
    Task UpdateUserAsync(User user);
    Task DeleteUserAsync(int id);
}

public interface IUserService
{
    Task<UserViewModel> GetUserAsync(int id);
    Task<IEnumerable<UserViewModel>> GetAllUsersAsync();
    Task<UserViewModel> CreateUserAsync(CreateUserRequest request);
}
```

**Step 2: Implement Interfaces**

```csharp
public class UserRepository : IUserRepository
{
    private readonly IDbContext _context;
    public UserRepository(IDbContext context)
    {
        _context = context ?? throw new ArgumentNullException(nameof(context));
    }
    // Implementation...
}

public class UserService : IUserService
{
    private readonly IUserRepository _userRepository;
    public UserService(IUserRepository userRepository)
    {
        _userRepository = userRepository ?? throw new ArgumentNullException(nameof(userRepository));
    }
    // Implementation...
}
```

### Phase 3: DI Container Configuration

**🔧 Service Registration in Program.cs**

```csharp
var builder = WebApplication.CreateBuilder(args);

builder.Services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(builder.Configuration.GetConnectionString("DefaultConnection")));

builder.Services.AddScoped<IUserRepository, UserRepository>();
builder.Services.AddScoped<IUserService, UserService>();
builder.Services.AddScoped<IEmailService, EmailService>();
builder.Services.AddScoped<INotificationService, NotificationService>();

var app = builder.Build();
```

### Phase 4: Testing Benefits

**🧪 Unit Testing with Mocks**

**Now you can easily test business logic in isolation:**

```csharp
[Test]
public async Task GetUserAsync_ReturnsUserViewModel_WhenUserExists()
{
    var mockRepository = new Mock<IUserRepository>();
    var user = new User { Id = 1, Name = "John Doe", Email = "john@example.com" };
    mockRepository.Setup(x => x.GetUserAsync(1)).ReturnsAsync(user);
    var service = new UserService(mockRepository.Object);

    var result = await service.GetUserAsync(1);

    Assert.NotNull(result);
    Assert.Equal("John Doe", result.Name);
    Assert.Equal("john@example.com", result.Email);
}
```

## 🔧 Advanced DI Patterns

**🏗️ Professional DI Patterns:**

* **Factory Pattern:** For creating complex object graphs
* **Decorator Pattern:** For adding behavior without changing classes
* **Strategy Pattern:** For runtime algorithm selection
* **Options Pattern:** For configuration injection
* **Keyed Services:** For multiple implementations of same interface

## 🎯 Learning Outcome Connection

**LO3: Implementation - Software Principles**

Dependency Injection demonstrates your ability to:

* **Apply SOLID principles:** Especially Dependency Inversion and Single Responsibility
* **Create maintainable code:** Loosely coupled, testable components
* **Implement professional patterns:** Industry-standard architectural approaches
* **Enable testing:** Unit testing with mocks and fakes

## 🚀 Next Steps

**⏭️ Ready for Advanced Testing?** Continue with [How to ensure only the (business) logic is unit tested?](unit-testing-practice.md) to learn how to test your business logic in complete isolation using the DI patterns you've mastered.

**🎯 Apply to Your Project:** Review your individual project's architecture. Are you using dependency injection effectively? Can you identify tightly coupled components that could benefit from DI? Consider refactoring critical components to use DI patterns.

*Dependency Injection isn't just a technique - it's a mindset. When you start thinking about dependencies as contracts rather than implementations, you unlock the power of flexible, maintainable software architecture.*
