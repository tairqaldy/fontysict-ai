# Class Diagram

# 📐 Class Diagram

Modeling the static structure of your software system

## 🎯 What is a Class Diagram?

**💡 Definition:** A class diagram provides an overview of the classes in a system, as well as the relationships between these classes. They model the **static structure** of your software.

### What Class Diagrams Show:

#### 📝 Class Names

The identity of each class in your system

#### 🏷️ Attributes

The data/properties that each class holds

#### ⚙️ Methods

The behavior/functions that each class provides

#### 🔗 Relationships

How classes connect and interact with each other

## 🚀 Why Use Class Diagrams?

**📘 Key Benefits:** Discuss and validate your design with colleagues **before** you start programming.

### Primary Uses:

* **Design Validation:** Review and discuss system structure with team members
* **Documentation:** Standard way to document your system's structure
* **Communication:** Bridge between technical and non-technical stakeholders
* **Implementation Guide:** Blueprint for coding the actual classes

**⚠️ Best Practice:** Create class diagrams during the design phase, not after coding. They're most valuable when used as a planning tool!

## 📊 Practical Example: Card Game

**💡 Domain Model:** Below is an example depicting a card game domain model, where each 'component' can be implemented as code.

![1770647717837](image/03-Class-Diagram/1770647717837.png)*Figure 1: Example class diagram for a card game*

## 💻 From Diagram to Code

**📘 Important:** Programming languages have different capabilities, so you may need to translate UML concepts to what your language supports.

### Example: Private String Attribute

Consider a private instance variable `name` of type `string` from the Player class:

#### 🔷 C# Implementation

C# is strongly typed with access modifier support:

`private string name;`

#### 🐍 Python Implementation

Python is dynamically typed with naming conventions for privacy:

`__name`*Note: The __ prefix follows [PEP8 coding style**Links to an external site.**](https://peps.python.org/pep-0008/#method-names-and-instance-variables) as a convention, not syntax.*

## 📚 UML Notation Reference

**💡 Cheat Sheet:** Quick reference for UML class diagram notation and symbols.

![1770647728933](image/03-Class-Diagram/1770647728933.png)*Figure 2: UML Class Diagram Cheat Sheet*

**💡 Pro Tip:** Keep this reference handy when creating your class diagrams - consistent notation makes your diagrams easier to read and understand!

## 📚 Learning Resources

**💡 Learning Path:** Start with the tutorial for fundamentals, then watch videos for practical examples and creation techniques.

### 📖 Tutorials & Guides

* **Comprehensive Tutorial:** [UML Class Diagram Tutorial**Links to an external site.**](https://www.tutorialspoint.com/uml/uml_class_diagram.htm) from TutorialsPoint

### 🎥 Video Tutorials

* **Fundamentals:** [UML Class Diagram Tutorial**Links to an external site.**](https://www.youtube.com/watch?v=UI6lqHOVHic)[![](https://fhict.instructure.com/images/play_overlay.png)](https://www.youtube.com/watch?v=UI6lqHOVHic)by Lucid Software
* **Practical Creation:** [Creating a Class Diagram**Links to an external site.**](https://www.youtube.com/watch?v=tKy85WODAUk)[![](https://fhict.instructure.com/images/play_overlay.png)](https://www.youtube.com/watch?v=tKy85WODAUk)by MOOC UML

*Part of the Software Design & Engineering course | Fontys ICT*
