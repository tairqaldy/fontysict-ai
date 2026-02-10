# Object Oriented Principles

# 🧩 Object-Oriented Principles

The four pillars of maintainable code design

## 🎯 What is Object-Oriented Programming?

**💡 Core Concept:** OOP structures code by dividing it into objects that have predefined logical relationships with each other.

### Why Use OOP?

#### 🏗️ Better Structure

Code is organized into objects, making it more structured and easier to understand

#### 🛠️ Easier Maintenance

Changes are localized to specific objects, reducing the impact on the entire system

#### 🔄 Code Reusability

Objects can be reused in a simple and logical manner across different parts of your application

### Building Blocks: Classes and Objects

Objects are defined by creating  **classes** , which consist of:

* **Fields (Class Variables):** Contain the properties and data of an object
* **Methods (Functions):** Define the actions and behaviors that can be performed

## 🏛️ The Four Fundamental Principles

**📘 Foundation:** A well-structured OOP project should take these principles into account to keep code manageable and maintainable.

**⚠️ Important Note:** These are  **principles, not laws** . You can choose to deviate from them, but only do so consciously when the situation demands it.

### The Four Pillars:

#### 1. 🔒 Encapsulation

Bundling data and methods together while restricting access to internal implementation details

#### 2. 🧬 Inheritance

Creating new classes based on existing classes, inheriting their properties and behaviors

#### 3. 🎭 Abstraction

Hiding complex implementation details while exposing only essential features

#### 4. 🌟 Polymorphism

The ability of objects to take multiple forms and respond differently to the same interface

## 🔒 Encapsulation

**💡 Definition:** Bundling data (attributes) and methods (functions) together while controlling access to the internal state of an object.

### Key Benefits:

* **Data Protection:** Prevents external code from directly modifying internal state
* **Controlled Access:** Access through public methods ensures validation and consistency
* **Flexibility:** Internal implementation can change without affecting external code

### Example Implementation:

`class BankAccount {<br/>  private decimal balance; // Encapsulated data<br/><br/>  public void Deposit(decimal amount) { // Controlled access<br/>    if (amount > 0) balance += amount;<br/>  }<br/><br/>  public decimal GetBalance() { return balance; }<br/>}`

## 🧬 Inheritance

**💡 Definition:** The mechanism where a new class (child/derived) inherits properties and methods from an existing class (parent/base).

### Key Benefits:

* **Code Reuse:** Avoid duplicating common functionality
* **Hierarchical Organization:** Create logical relationships between classes
* **Extensibility:** Add new features while maintaining existing functionality

### Example Implementation:

`class Vehicle {<br/>  public string Brand { get; set; }<br/>  public void Start() { ... }<br/>}<br/><br/>class Car : Vehicle { // Inherits from Vehicle<br/>  public int Doors { get; set; }<br/>  public void OpenTrunk() { ... }<br/>}`

## 🎭 Abstraction

**💡 Definition:** Hiding complex implementation details while exposing only the essential features and functionality to the user.

### Key Benefits:

* **Simplified Interface:** Users work with simple, clear interfaces
* **Reduced Complexity:** Hide unnecessary implementation details
* **Focus on Behavior:** Emphasize what an object does, not how it does it

### Example Implementation:

`abstract class Shape {<br/>  public abstract double CalculateArea(); // Abstract method<br/>}<br/><br/>class Circle : Shape {<br/>  private double radius;<br/>  public override double CalculateArea() {<br/>    return Math.PI * radius * radius;<br/>  }<br/>}`

## 🌟 Polymorphism

**💡 Definition:** The ability of objects of different types to be treated as instances of the same type through a common interface, while responding differently to the same method calls.

### Key Benefits:

* **Flexible Code:** Same interface, different implementations
* **Runtime Decisions:** Behavior determined at runtime based on actual object type
* **Extensibility:** Easy to add new types without changing existing code

### Example Implementation:

`Animal[] animals = { new Dog(), new Cat() };<br/><br/>foreach (Animal animal in animals) {<br/>  animal.MakeSound(); // Dog barks, Cat meows<br/>}`

## 📚 Learning Resources

**💡 Learning Path:** Start with the comprehensive FreeCodeCamp article, then dive into GeeksforGeeks for technical details and examples.

### 📖 Essential Reading

* **Comprehensive Guide:** [Object-Oriented Programming Concepts**Links to an external site.**](https://www.freecodecamp.org/news/object-oriented-programming-concepts-21bb035f7260/) by FreeCodeCamp
* **Technical Deep Dive:** [Introduction to Object-Oriented Programming**Links to an external site.**](https://www.geeksforgeeks.org/introduction-of-object-oriented-programming/) by GeeksforGeeks

**⚠️ Practice Tip:** Don't just read about these principles - practice implementing them in your code. Start with simple examples and gradually work toward more complex applications.

*Part of the Software Design & Engineering course | Fontys ICT*
