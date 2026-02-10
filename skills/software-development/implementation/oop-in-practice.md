# Object-Oriented Programming in Practice

> Source: Canvas > Software Development Skills > Implementation
> Last updated: 2026-02-10
> Status: complete

# 🧩 Object-Oriented Programming in Practice

Move beyond syntax to master OOP design patterns and principles

**⚠️ Beyond the Basics:** You already know what classes and objects are. This workshop focuses on practical OOP skills that professional developers use daily: designing maintainable class hierarchies, applying encapsulation effectively, and building extensible systems.

**🎯 Workshop Goal:** Master practical OOP design by building a real-world application. Learn to apply the four pillars of OOP in ways that make your code maintainable, testable, and extensible.

## 🏛️ The Four Pillars of OOP (Applied)

**🔒 Encapsulation: Data Protection**

**Beyond getters/setters:** True encapsulation means protecting object invariants and business rules.

* Use private fields and controlled access
* Validate data before setting values
* Protect object state consistency

**🧬 Inheritance: Code Reuse & Hierarchy**

**Beyond extending classes:** Create meaningful is-a relationships that reflect real-world hierarchies.

* Use inheritance for genuine specialization
* Favor composition over inheritance when appropriate
* Apply the Liskov Substitution Principle

**🎭 Polymorphism: Runtime Flexibility**

**Beyond method overriding:** Design systems that can work with different types through common interfaces.

* Use virtual methods and interfaces strategically
* Enable runtime type switching
* Support the Open/Closed Principle

**🎯 Abstraction: Hiding Complexity**

**Beyond hiding implementation:** Create clear interfaces that expose only what clients need to know.

* Design intuitive public APIs
* Use abstract classes and interfaces appropriately
* Separate what from how

## 🛠️ Prerequisites & Setup

**🧠 Essential Knowledge:**

* Basic C# syntax and programming concepts
* Understanding of classes, objects, and methods
* [Object Oriented Principles](../../resources/design/oop-principles.md)
* Review: [Classes in C#](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/tutorials/classes)
* Review: [OOP Principles in C#](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/tutorials/oop)

**📊 UML Preparation:**

* Create a simple [class diagram](../../resources/design/class-diagram.md) for a banking application
* Use [draw.io](https://www.drawio.com/blog/uml-class-diagrams) or paper - keep it simple!
* Focus on class names and relationships (associations)

## 🏦 Challenge: Banking System Design

**🎯 Real-World Application**

Design and implement a banking system that demonstrates all four OOP principles in practice. This isn't just a coding exercise - it's about applying design thinking to create maintainable, extensible software.

**System Requirements:**

* Support multiple account types (Savings, Checking, Credit)
* Handle transactions (Deposit, Withdrawal, Transfer)
* Implement business rules (overdraft protection, interest calculation)
* Persist data to a database without ORM
* Support future extensibility (new account types, transaction types)

### Phase 1: OOP Design Discussion

**🤝 Team Discussion Points:**

* **Classes vs Objects:** What's the practical difference in your banking system?
* **Encapsulation:** What business rules need protection?
* **Inheritance:** How should different account types relate?
* **Polymorphism:** Where would runtime type switching be useful?
* **Abstraction:** What should clients of your system know/not know?

**💡 Design Thinking Questions:**

* How would you handle insufficient funds for withdrawals?
* What happens when you need to add a new account type?
* How can you ensure account balances are never inconsistent?
* What interface should other systems use to interact with accounts?

### Phase 2: Implementation with Database Integration

**💾 Database Integration Challenge**

**Technical Requirements:**

* Use raw SQL (no ORM) to persist account data
* Implement proper SQL parameterization for security
* Handle database connections and transactions
* Maintain OOP principles in data access code

**Resources:**

* [SqlCommand Documentation](https://learn.microsoft.com/en-us/dotnet/api/system.data.sqlclient.sqlcommand)
* [SQL Parameters Guide](https://learn.microsoft.com/en-us/dotnet/api/system.data.sqlclient.sqlcommand.parameters)

**🎯 OOP Integration Guidelines:**

* **Encapsulation:** Hide database details from business logic
* **Separation of Concerns:** Keep data access separate from domain logic
* **Dependency Injection:** Make database connections configurable
* **Error Handling:** Encapsulate database errors in domain exceptions

### Phase 3: Design Evolution & Documentation

**📊 Update Your Design:**

* **Refine your UML diagram** to reflect actual implementation
* **Document design decisions** - why did you choose certain approaches?
* **Identify areas for improvement** - what would you change?
* **Plan for extensibility** - how would you add new features?

**💡 Reflection Questions:**

* Why use SQL parameters instead of string concatenation?
* How does your design support different account types?
* What business rules are enforced by your classes?
* How would you test your banking system components?

## 🎯 Learning Outcome Connection

**LO3: Implementation - Software Principles**

This workshop demonstrates your ability to:

* **Apply OOP principles:** Use encapsulation, inheritance, polymorphism, and abstraction effectively
* **Design maintainable code:** Create class hierarchies that support evolution
* **Integrate with databases:** Use relational databases for data persistence
* **Ensure security:** Apply SQL parameterization and proper data validation

## 🚀 Next Steps

**⏭️ Ready for Testing?** Continue with [Acceptance Testing and Unit Testing](acceptance-unit-testing.md) to learn how to validate your OOP design with proper testing strategies.

**🎯 Apply to Your Project:** Review your individual project's class design. Are you applying OOP principles effectively? Can you identify areas where better encapsulation, inheritance, or polymorphism would improve your code?

*Good object-oriented design isn't about using every feature of OOP - it's about choosing the right abstractions that make your code easier to understand, maintain, and extend.*
