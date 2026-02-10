# How to start designing maintainable code?

# 🏗️ Designing Maintainable Code

Transform spaghetti code into sustainable software architecture

**⚠️ The Technical Debt Crisis:** 85% of development time is spent maintaining existing code, not building new features. Why? Because most code is written once and modified hundreds of times. The difference between sustainable code and technical debt is architecture.

![Maintainable Code Meme showing the reality of code maintenance](https://fhict.instructure.com/courses/15759/files/2576787/preview)

**🎯 Workshop Goal:** Learn to design layered architecture that separates concerns, enables testing, and allows for safe modifications. Turn your individual project into enterprise-grade software.

## 💰 The Business Case for Maintainable Code

**📈 Future-Proof Your Code**

Imagine your semester project becomes a real product used by thousands. Your code needs to handle:

* **New features** requested by customers
* **Bug fixes** discovered in production
* **Technology updates** to stay compatible
* **Team development** with multiple developers

**🔧 Maintainability = Productivity**

Well-structured code enables:

* **Safe modifications** without breaking existing features
* **Team collaboration** with clear code ownership
* **Faster debugging** with isolated components
* **Easier testing** with separated concerns

## 🛠️ Prerequisites & Setup

 **🧠 Essential Knowledge:** * [Class diagram analysis](https://fhict.instructure.com/courses/15759/pages/class-diagram) and creation

* [Object-oriented programming](https://fhict.instructure.com/courses/15759/pages/object-oriented-programming-in-practice) fundamentals
* [Layered architecture](https://fhict.instructure.com/courses/15759/pages/layered-architecture) concepts

## 💬 Discussion & Questions

Questions about code architecture and maintainability?

[💬 Join Architecture Discussion](https://fhict.instructure.com/courses/15759/discussion_topics/94076)

## 🎮 Challenge: Bingo App Refactoring

**🎯 The Scenario: Legacy Code Nightmare**

You've inherited a Bingo application that works... barely. It's a classic example of "everything in one class" syndrome. Your mission: transform it into maintainable, extensible software.

**📥 Download:** [Legacy Bingo Application](https://fhict.instructure.com/courses/15759/files/2576789?verifier=cZVSIi6PMkNZDMZNXsyUfz0pGvxux5bQE6H5YbFG&wrap=1)

**Current Features:**

* Start & stop games
* Save/load games from files
* Basic Windows Forms UI

**Required New Features:**

* Database storage support
* Game history viewer
* Import legacy saved games
* Multiple storage backends

### Phase 1: Code Archaeology

**🔍 Detective Work:** Analyze the existing codebase and identify maintainability issues:* **God Object:** Is everything in one massive class?

* **Mixed Concerns:** UI logic mixed with business logic?
* **Hard Dependencies:** File I/O directly in UI components?
* **Code Duplication:** Same logic repeated in multiple places?
* **Testability:** How would you unit test this code?

**🏗️ Design Better Architecture**

Create a UML class diagram showing a layered architecture:

* **Business Logic Layer:** Game rules, scoring, validation
* **Data Access Layer:** Storage abstraction (files, database)
* **Service Layer:** Application workflows and coordination
* **Integration Layer:** External dependencies and adapters

### Phase 2: Collaborative Feature Design

**🤝 Team Challenge:** Work in pairs to design one feature each:* **Team 1:** Database storage with file backward compatibility

* **Team 2:** Game history viewer with search and filtering
* **Team 3:** Legacy data import with validation

 **💡 Design Principles:** * **Single Responsibility:** Each class has one job

* **Open/Closed:** Open for extension, closed for modification
* **Dependency Inversion:** Depend on abstractions, not concretions
* **Interface Segregation:** Many specific interfaces > one general interface

### Phase 3: Implementation Strategy

**⚡ Refactoring Approach**

**Step-by-step transformation:**

1. **Extract business logic** from UI components
2. **Create data access abstractions** (Repository pattern)
3. **Implement service layer** for application workflows
4. **Add dependency injection** for loose coupling
5. **Test each layer independently**

## 🚀 Optional: Implementation Track

 **🎯 Choose Your Path:** **Option A: New GUI Development*** Build a console or web interface using your new architecture

* Implement game history viewer
* Add storage type selection
* Create import functionality with [sample data](https://fhict.instructure.com/courses/15759/files/2576790?verifier=MxdKkhLuoMyewB4KGVMYvHsOQHXCGT69eBAMBVfS&wrap=1)

**Option B: Unit Testing Focus*** Create comprehensive unit tests for business logic

* Test data access layer with mocked dependencies
* Validate import functionality with edge cases
* Demonstrate testability improvements

## 🎯 Learning Outcome Connection

**LO2: Design & LO3: Implementation**

This workshop bridges design and implementation by demonstrating:

* **Maintainable design:** Architecture that supports future changes
* **Security considerations:** Proper separation of concerns
* **Software principles:** SOLID principles in practice
* **Iterative development:** Refactoring and continuous improvement

## 🚀 Next Steps

**⏭️ Ready for Advanced Architecture?** Continue with [SOLID Principles](https://fhict.instructure.com/courses/15759/pages/how-can-solid-help-with-designing-maintainable-code) to master the five fundamental design principles that make code truly maintainable.

**🎯 Apply to Your Project:** Take the architectural lessons learned here and apply them to your individual project. Clean architecture from the start is much easier than refactoring later.

*⚖️ Architecture Truth: Perfect code doesn't exist, but maintainable code does. Focus on clarity, testability, and separation of concerns over clever solutions.*
