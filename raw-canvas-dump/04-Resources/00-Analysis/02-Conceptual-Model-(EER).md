# Conceptual Model (EER)

# 🗺️ Conceptual Model (EER)

Creating a domain model that speaks the client's language

## 🎯 What is a Conceptual Model?

**💡 Key Purpose:** A conceptual model serves as a discussion tool with the client and contains no technical details, but rather uses **"the language of the client."**

It is useful to create a conceptual model early in the project to structure the application's domain. This model bridges the gap between business requirements and technical implementation.

### What to Include:

#### 📦 Entities

The main "things" or objects in the domain (e.g., Customer, Product, Order)

#### 🔗 Relationships

How entities connect to each other (e.g., Customer places Order)

#### 🏷️ Main Attributes

Key properties relevant to the application (e.g., Customer name, Product price)

### What to Avoid at This Stage:

**⚠️ Keep It Non-Technical:** Avoid making technical decisions such as:* "What type should each attribute have?"

* "How will this be stored in the database?"
* "Which system behaviours belong to which entity?"

## 📊 EER Example

**📘 Example:** Below is an Enhanced Entity-Relationship (EER) diagram showing entities, relationships, and key attributes in a client-friendly format.

![1770647377453](image/02-Conceptual-Model-(EER)/1770647377453.png)

Once you have created a conceptual model, you will have a solid analysis of the client domain, allowing you to start translating these requirements into a technical solution.

## 🌐 Optional: Context Diagram

**💡 Additional Tool:** A context diagram can complement your conceptual model by showing how your application interacts with external systems and actors.

In addition to a conceptual model, such as an EER, it can also be useful to include a context diagram. This diagram depicts how the application 'interacts' with external systems and the actors.

### What a Context Diagram Shows:

* **Users:** Who will interact with the system
* **External APIs:** Third-party services the application uses
* **Hardware/Software:** Other systems that interact with your application
* **High-level view:** Your application as a "black box" with external collaborators

![1770647401356](image/02-Conceptual-Model-(EER)/1770647401356.png)

## 📚 Learning Resources

**💡 Pro Tip:** Start with the presentation to understand the fundamentals, then explore the additional resources for deeper understanding of different EER notations.

#### 📖 Conceptual Model Resources

* **Presentation:** [How to create a conceptual diagram](https://fhict.instructure.com/courses/15759/files/2576972?verifier=PoZntfVMbFnFPs8RBiQ13rrT4oAXZY6EQgIAhpbv&wrap=1)
* **Chen's Notation:** [ER Model (Chen&#39;s notation)**Links to an external site.**](https://www.softwareideas.net/chen-er-diagram-erd) from softwareideas.net
* **Enhanced ER:** [Enhanced ER Model**Links to an external site.**](https://www.geeksforgeeks.org/enhanced-er-model/) from geeksforgeeks.org

#### 🌐 Context Diagram Resources

* **C4 Model:** [Context Diagram**Links to an external site.**](https://c4model.com/diagrams/system-context) from c4model.com

*Part of the Software Design & Engineering course | Fontys ICT*
