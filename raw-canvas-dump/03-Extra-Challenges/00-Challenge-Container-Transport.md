# Challenge Container Transport

# 🚢 Container Transport Challenge

Optimize cargo ship loading through algorithmic container arrangement

## 🎯 The Challenge Context

Container transport company **Berend Bootje** wants to automate the planning and arrangement of containers on their cargo ships. This currently takes too much time and time is money. There is quite a lot involved in creating a good arrangement.

**💡 Challenge Goal:** Create a program that can automatically generate optimal container layouts for cargo ships, considering all weight, placement, and safety constraints.

## ⚙️ Technical Requirements

Your solution should include:

* **Class Diagram:** Design a comprehensive object-oriented model
* **Algorithm Implementation:** Create efficient container placement logic
* **Unit Testing:** Implement tests to validate all constraint violations
* **Visualization:** Generate clear layouts showing container placement per layer
* **User Interface:** Allow specification of container types and quantities

## 📋 Container & Ship Rules

### Weight Constraints

* **Maximum stack weight:** 120 tons maximum on top of any container
* **Container weight:** Full containers weigh maximum 30 tons
* **Empty containers:** Always weigh 4000 kg (4 tons)

### Special Container Types

* **Valuable cargo:** Nothing may be stacked on top; must be accessible from front or back
* **Refrigerated containers:** Must be placed in first row (front) due to power connections

### Ship Safety Requirements

* **Minimum load:** At least 50% of maximum ship capacity must be used
* **Balance requirement:** Weight distribution between left/right halves may not differ by more than 20%
* **Configurable dimensions:** Ship length and width must be adjustable in containers

**⚠️ Critical Safety Rule:** All constraints must be validated - violation of any rule could result in cargo damage or ship capsizing!

## 🎮 3D Visualization Tool

Rather than building your own visualization from scratch, you can use the **Container Visualizer** developed by Jan Oonk in Unity 3D:

[🚀 Launch Container Visualizer **Links to an external site.**](https://i872272.luna.fhict.nl/ContainerVisualizer/index.html?length=1&width=1&stacks=1&weights=1)

### URL Parameter Format

| Parameter          | Symbol      | Description                                           |
| ------------------ | ----------- | ----------------------------------------------------- |
| Container & Weight | `--`      | Separates container type from weight                  |
| Row Separator      | `/`       | Separates ship rows                                   |
| Empty Stack        | `,,`      | Indicates empty position                              |
| Container Types    | `1,2,3,4` | 1=Normal, 2=Valuable, 3=Coolable, 4=Valuable+Coolable |

### Example URLs

**Single Container:**
[Simple 1x1 Layout**Links to an external site.**](https://i872272.luna.fhict.nl/ContainerVisualizer/index.html?length=1&width=1&stacks=1&weights=1)

**2x2 Grid:**
[2x2 Container Grid**Links to an external site.**](https://i872272.luna.fhict.nl/ContainerVisualizer/index.html?length=2&width=2&stacks=1,1/1,1&weights=1,1/1,1)

**Complex Stacking:**
[3x3 with Stacking**Links to an external site.**](https://i872272.luna.fhict.nl/ContainerVisualizer/index.html?length=3&width=3&stacks=1-1-1,1-1-1,1-1-1/1-1-1,1-1-1,1-1-1/1-1-1,1-1-1,1-1-1&weights=1-1-1,1-1-1,1-1-1/1-1-1,1-1-1,1-1-1/1-1-1,1-1-1,1-1-1)

**💡 Integration Challenge:** Modify your application to export layouts as URLs for the visualization tool. The tool calculates quality metrics like Height Variance and Weight Distribution - can you achieve the most optimal arrangement?

## 🎓 Learning Outcomes Connection

This challenge directly supports multiple S2 learning outcomes:

#### LO1: Analysis

Analyze complex business requirements and translate them into technical specifications

#### LO2: Design

Create maintainable object-oriented designs using UML class diagrams

#### LO3: Implementation

Apply SOLID principles and implement complex algorithms with proper validation

#### LO4: Testing

Implement comprehensive unit tests to validate constraint handling

## 💭 Reflection & Next Steps

Use this challenge as a foundation for portfolio evidence and technical discussions. The complexity allows you to demonstrate your current capabilities while identifying areas for growth.

**📘 Portfolio Connection:** Document your approach, design decisions, and technical challenges. This evidence directly supports your learning outcome demonstrations and provides rich material for assessment discussions.

**Key reflection questions:**

* How did you approach the constraint satisfaction problem?
* What design patterns emerged in your solution?
* How did you ensure code maintainability and testability?
* What trade-offs did you make in your optimization algorithm?

Discuss your progress and challenges with your technical coach to align this work with your individual project planning.

### Ready to tackle the challenge?

Start with analysis and design before diving into implementation. Good luck!
