# Challenge Visitor Placement Tool

# 🎪 Visitor Placement Tool Challenge

Intelligent seating algorithms for optimal event visitor placement

## 🎯 The Challenge Context

Event organizers need an intelligent tool that automatically assigns optimal seating positions to visitors. The challenge involves managing variable venue layouts, complex group requirements, and ensuring the best possible viewing experience for all attendees.

**💡 Core Challenge:** Create an algorithm that balances optimal seating (children in front, groups together) with efficient space utilization and complex registration constraints.

## ⚙️ Technical Design Requirements

Your solution must demonstrate:

* **Domain Modeling:** Comprehensive class diagram showing all entities and relationships
* **User Journey:** Clear scenarios mapping the visitor placement workflow
* **Algorithm Design:** Flowchart documenting the placement optimization logic
* **SOLID Principles:** Application of [SOLID principles](https://fhict.instructure.com/courses/15759/pages/how-can-solid-help-with-designing-maintainable-code) for maintainable code
* **Unit Testing:** Comprehensive test coverage for placement logic

## 🏟️ Venue Layout Specifications

### Section Structure

* **Variable sections:** Each section has 1-3 rows depending on course obstacles
* **Consistent row length:** All rows within a section have identical length
* **Row capacity:** Each row contains 3-10 chairs
* **Unique identification:** Sections have letters (A, B, C...), rows have numbers, chairs have codes (e.g., A1-2, B2-5)

![1770647100688](image/01-Challenge-Visitor-Placement-Tool/1770647100688.png)

**📘 Layout Goal:** Use minimum sections while maximizing chair utilization. Sections don't need to be opened sequentially (you can open C while B remains empty).

## 👥 Visitor Registration & Placement Rules

### Registration System

* **Individual or group registration:** Visitors (adults/children ≤12) can register alone or in groups
* **First-time visitors:** Must register with name and birthdate, receive unique ID
* **Access control:** Late registrations denied, capacity limits enforced (first-come, first-served)
* **Duplicate prevention:** Visitors cannot register twice for same event

### Placement Algorithm Requirements

* **Child priority:** Children always placed in front rows for optimal viewing
* **Group supervision:** Children must register with ≥1 adult, always seated with adult supervision
* **Group cohesion:** Prefer placing entire groups in single rows, split intelligently when necessary
* **Proximity optimization:** When groups split, maintain minimum row distance between subgroups

**⚠️ Complex Constraint:** Large child groups may require splitting across sections, with each subgroup maintaining adult supervision and proximity to other subgroups.

## 🔧 Implementation Features

### Core Functionality

* **Placement visualization:** Display person and group IDs on chairs using ASCII, Unity 3D, or bitmap graphics
* **Access reporting:** Generate lists of denied visitors with specific reasons
* **Data management:** Support for JSON file import/export for visitor lists
* **Test data generation:** Random visitor list generator for testing scenarios

### Technical Implementation

* **Unit testing:** Comprehensive test coverage for all placement algorithms
* **Color coding:** Visual indicators for different visitor types and group memberships
* **Algorithm optimization:** Efficient space utilization with minimal empty chairs
* **Constraint validation:** Robust checking of all business rules

**💡 Visualization Inspiration:** Check out the [Container Transport Challenge](https://fhict.instructure.com/courses/15759/pages/challenge-container-transport) for 3D visualization techniques using Unity 3D.

## 🎓 Learning Outcomes Connection

This challenge demonstrates mastery across multiple S2 learning outcomes:

#### LO1: Analysis

Complex constraint analysis, user journey mapping, and business rule documentation

#### LO2: Design

Domain modeling, algorithm design, and SOLID principle application

#### LO3: Implementation

Complex algorithm implementation, data persistence, and visualization components

#### LO4: Testing

Unit testing for placement algorithms, constraint validation, and edge case handling

## 🧩 Algorithm Design Challenges

Consider these algorithmic challenges in your implementation:

#### Constraint Satisfaction

Balance competing requirements: child front-row priority vs. group cohesion vs. space efficiency

#### Optimization Problem

Minimize sections used while maximizing chair utilization and maintaining group proximity

#### Dynamic Planning

Handle variable section sizes and adapt placement strategy based on current venue configuration

## 💭 Reflection & Portfolio Development

This challenge offers rich opportunities for demonstrating technical depth and problem-solving skills. Focus on documenting your approach to complex algorithmic challenges.

**📘 Portfolio Gold:** Document your algorithm iterations, constraint handling strategies, and performance optimizations. This demonstrates advanced problem-solving capabilities.

**Key reflection areas:**

* How did you approach the multi-constraint optimization problem?
* What trade-offs did you make between different placement strategies?
* How did you handle edge cases (large child groups, capacity limits)?
* What data structures best supported your algorithm's efficiency?
* How did you ensure your solution scales with venue size?

Use this challenge as a foundation for technical discussions with your coach. The complexity demonstrates advanced software engineering capabilities beyond basic CRUD operations.

### Ready to solve the placement puzzle?

Start with domain modeling and constraint analysis. The algorithm design is where the real challenge begins!
