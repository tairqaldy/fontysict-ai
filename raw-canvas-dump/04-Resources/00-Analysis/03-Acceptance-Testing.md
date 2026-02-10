# Acceptance Testing

# ✅ Acceptance Testing

Ensuring your solution meets user requirements

## 🎯 What is User Acceptance Testing (UAT)?

**💡 Key Goal:** Ensure that the solution fulfills the (non-)functional requirements and all their specific constraints and criteria as defined in the analysis phase.

### Core Principles of UAT:

#### 👥 End User Perspective

Tests are conducted from the perspective of the end user, not the developer

#### 🏭 Production-like Environment

Performed on an environment that closely resembles production, including integrations

#### 🛡️ Risk Reduction

Helps reduce risks post-release by catching issues before delivery

**⚠️ Pro Tip:** Start writing test cases early in your development cycle - they're closely tied to your requirements and use cases. It's often the final step before software delivery.

## 🔄 Acceptance Testing in the development Process

![1770647456802](image/03-Acceptance-Testing/1770647456802.png)

## 📋 Writing Test Cases

**💡 Structure:** Here's a possible structure for an acceptance test case based on a functional requirement.

### Example Test Case Structure:

**Requirement:** "The car dealer can add a new car to the inventory."

* **Test Case ID:** TC-001-01
* **Description:** Verify dealer can add a new car to inventory
* **Preconditions:** Dealer is logged in and on the "Add Car" page
* **Steps:**
  1. Enter car details: make, model, year, VIN, and price
  2. Click "Save"
* **Expected Result:** Car is added to inventory, and a success message is displayed
* **Actual Result:** *(to be filled during test execution)*

**⚠️ Important:** Test cases should be written so that a user without technical background or system knowledge can perform the test. Keep it simple and clear!

## 📊 Test Case Examples

**📘 ID Structure:** Test case IDs can reference relevant requirements or use cases (e.g., TC-001-01 where the first number matches a use case).

![1770647468510](image/03-Acceptance-Testing/1770647468510.png)*Figure 1: Example test cases*

You might find that test cases resemble your use cases - both define preconditions and steps. You can structure test cases to reference a use case and its particular flow, then only provide the input values to be used.

## 🔗 Traceability Matrix

**💡 Coverage Check:** To ensure all requirements, constraints, and quality criteria are covered, create a traceability matrix.

A traceability matrix helps you verify complete coverage:

* **Empty columns:** May prompt you to add missing test cases
* **Empty rows:** Suggest adding requirements or requirement specifications

![1770647477007](image/03-Acceptance-Testing/1770647477007.png)*Figure 2: Test Matrix*

## 📄 Test Report

When a user executes the test cases, the actual results can be recorded in a test report.

### A Test Report Should Include:

* **Actual Results:** What happened during test execution
* **Recommendations:** Based on results - release ready or postpone?
* **Requirement Revisions:** Do requirements need to be updated?
* **Additional Insights:** What else do the results suggest?

## 🤖 Test Automation

**📘 Advanced Topic:** While not formally part of this semester, automated end-to-end testing can be a good addition to manual UAT.

**⚠️ Important:** Automated frameworks do **not** fully replace manual UAT - they complement it.

### Automation Examples (Optional):

* **Selenium:** [Selenium tests example](https://fhict.instructure.com/courses/15759/files/2576820?verifier=Vo9EXmimhglDuWeuZ6r8uTQH2F61tzhsyEvnniWG&wrap=1) in .NET
* **Playwright:** [Playwright examples**Links to an external site.**](https://playwright.dev/dotnet/docs/intro#add-example-tests) for .NET

## 📚 Additional Resources

**💡 Pro Tip:** Start with the Dutch resource for fundamentals, then explore the international articles for broader perspectives on UAT best practices.

### 📖 Recommended Reading

* **Dutch Resource:** [Test Cases documentation**Links to an external site.**](https://rubensteins.github.io/s2-db-documentatie/Onderwerpen/TestCases) (NL)
* **UAT Overview:** [User Acceptance Testing guide**Links to an external site.**](https://www.altexsoft.com/blog/user-acceptance-testing/) by AltexSoft
* **Step-by-Step Guide:** [Acceptance Testing guide**Links to an external site.**](https://www.functionize.com/automated-testing/acceptance-testing-a-step-by-step-guide) by Functionize
* **Test Case Writing:** [How to write test cases**Links to an external site.**](https://www.coursera.org/articles/how-to-write-test-cases) by Coursera
* **Technical Deep Dive:** [Test Case fundamentals**Links to an external site.**](https://www.geeksforgeeks.org/test-case/) by GeeksforGeeks
* **Templates:** Search Google for [&#34;test case templates&#34;**Links to an external site.**](https://www.google.com/search?q=test+case+templates) for ready-to-use formats

*Part of the Software Design & Engineering course | Fontys ICT*
