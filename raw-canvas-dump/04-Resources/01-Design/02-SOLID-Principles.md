# SOLID Principles

# 🏗️ SOLID Principles

Five fundamental principles for object-oriented design and programming

## 🎯 What are SOLID Principles?

**💡 Core Concept:** SOLID is an acronym for five design principles that help create maintainable, scalable, and robust object-oriented software.

Originally introduced by Robert Martin (Uncle Bob), these principles guide developers in writing code that is:

* **Easy to maintain** - Changes don't break existing functionality
* **Flexible and extensible** - New features can be added without major refactoring
* **Testable** - Components can be tested in isolation
* **Readable and understandable** - Code intent is clear to other developers

**⚠️ Important Note:** These are  **principles, not laws** . Use them as guidelines to write better code, but remember that context matters and sometimes breaking a principle might be the right choice.

## S - Single Responsibility Principle

**💡 Definition:** A class should have one (and only one) origin of change.

### ❌ Problematic Situation

Consider a `BankClient` class that handles both client data and database operations. What if in the future we want to:

* Use a different database system
* Apply interest to the balance

This class has  **multiple reasons to change** , violating the SRP.

![1770647599299](image/02-SOLID-Principles/1770647599299.png)

### ✅ Solution

Separate concerns by creating distinct classes:

* `ClientDAL` - Handles database operations
* `BankAccount` - Manages account-related operations
* `BankClient` - Focuses purely on client information

![1770647607854](image/02-SOLID-Principles/1770647607854.png)

**💡 Key Benefit:** Each class now has a single, well-defined responsibility and only one reason to change.

## O - Open-Closed Principle

**💡 Definition:** Software entities should be open for extension but closed for modification.

### ❌ Problematic Situation

A `BankAccount` class with hardcoded interest calculations. Adding new interest types requires modifying existing code, affecting other classes.

![1770647615848](image/02-SOLID-Principles/1770647615848.png)

### ✅ Solution

Use interfaces and dependency injection:

`interface IInterest {<br/>  decimal ApplyInterest(decimal balance);<br/>}<br/><br/>class BankAccount {<br/>  private IInterest interestPlan;<br/>  // Uses interestPlan.ApplyInterest(balance)<br/>}`

**💡 Key Benefit:** New interest types can be added by implementing `IInterest` without modifying existing code.

![1770647626405](image/02-SOLID-Principles/1770647626405.png)

## L - Liskov Substitution Principle

**💡 Definition:** Objects in a program should be replaceable with instances of their sub-types without altering the correctness of that program.

### ❌ Problematic Situation

A `Square` class inheriting from `Rectangle`. While geometrically logical, it breaks substitutability:

`class Square : Rectangle {<br/>  public void setWidth(int width) {<br/>    m_width = width;<br/>    m_height = width; // Unexpected behavior!<br/>  }<br/>}`

### ✅ Solution

Create a common base class `Shape` that both `Rectangle` and `Square` can implement appropriately without violating expected behavior.

![1770647636150](image/02-SOLID-Principles/1770647636150.png)

**💡 Key Benefit:** Any `Shape` can be replaced with its subclasses without breaking functionality.

## I - Interface Segregation Principle

**💡 Definition:** Many client-specific interfaces are better than one general-purpose interface.

### ❌ Problematic Situation

A `DepositAccount` that implements `IBankAccount` but doesn't need deposit/withdraw functionality. It's forced to implement methods it shouldn't use.

![1770647643732](image/02-SOLID-Principles/1770647643732.png)![image-384bff71-be0b-45c5-abb4-bb3f9e3b9c20.png](https://fhict.instructure.com/courses/15759/files/2576773/preview)

### ✅ Solution

Split the interface into smaller, focused interfaces:

* `IPaymentAccount` - For deposit/withdraw/transfer operations
* `IInterestAccount` - For interest calculations

Now different account types can implement only the interfaces they need:

* **PaymentAccount:** Implements `IPaymentAccount`
* **SavingAccount:** Implements both interfaces
* **DepositAccount:** Implements only `IInterestAccount`

**💡 Key Benefit:** Classes aren't forced to depend on methods they don't use, reducing coupling and improving maintainability.

## D - Dependency Inversion Principle

**💡 Definition:** One should depend upon abstractions, not concretions.

### ❌ Problematic Situation

A `ClientDAL` class directly dependent on `FileAccess`. This tight coupling makes it impossible to use different storage systems without modifying the DAL.

![1770647651971](image/02-SOLID-Principles/1770647651971.png)

### ✅ Solution

Introduce an abstraction layer:

`interface IStorageAccess {<br/>  void Save(string data);<br/>  string Load();<br/>}<br/><br/>class ClientDAL {<br/>  private IStorageAccess storage;<br/>  // Uses storage interface, not concrete implementation<br/>}`

![1770647660390](image/02-SOLID-Principles/1770647660390.png)

Now `ClientDAL` can work with any storage implementation: `FileAccess`, `DatabaseAccess`, `CloudAccess`, etc.

**💡 Key Benefit:** High-level modules are no longer dependent on low-level implementation details, making the system more flexible and testable.

## 📚 Learning Resources

**💡 Learning Path:** Start with Uncle Bob's original articles, then explore practical implementations and real-world examples.

### 📖 Essential Reading

* **Original Source:** [Principles and Patterns**Links to an external site.**](https://web.archive.org/web/20150906155800/http://www.objectmentor.com/resources/articles/Principles_and_Patterns.pdf) by Robert C. Martin (Uncle Bob)
* **Practical Guide:** [SOLID Principles Explained in Plain English**Links to an external site.**](https://www.freecodecamp.org/news/solid-principles-explained-in-plain-english/) by FreeCodeCamp
* **With Examples:** [SOLID Principles with Real-Life Examples**Links to an external site.**](https://www.geeksforgeeks.org/solid-principle-in-programming-understand-with-real-life-examples/) by GeeksforGeeks

### 🎯 Related Topics

* [Object-Oriented Principles](https://fhict.instructure.com/courses/15759/pages/object-oriented-principles-2) - Foundation concepts for SOLID
* [How can SOLID help with designing maintainable code?](https://fhict.instructure.com/courses/15759/pages/how-can-solid-help-with-designing-maintainable-code) - Practical implementation

**⚠️ Practice Tip:** Don't try to apply all SOLID principles at once. Start with Single Responsibility and gradually incorporate others as you become more comfortable with the concepts.

### 🎯 Remember: SOLID principles work together

Each principle reinforces the others to create maintainable, flexible, and robust object-oriented code. Practice applying them gradually in your projects.

*Part of the Software Design & Engineering course | Fontys ICT*
