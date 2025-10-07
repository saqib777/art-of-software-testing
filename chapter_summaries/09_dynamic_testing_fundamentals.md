# Chapter 9 — Dynamic Testing Fundamentals

> “Testing shows the presence of defects, not their absence.” — *Edsger Dijkstra*

---

## 1. Introduction

Dynamic testing is the **process of executing code or a system to observe its behavior**, verify its correctness, and identify defects.  
Unlike **static testing** (reviews, walkthroughs, inspections), dynamic testing *runs* the product.

The goal is not merely to find bugs but to **demonstrate that the software behaves as intended** in real conditions.

---

## 2. Static vs Dynamic Testing

| Aspect | Static Testing | Dynamic Testing |
|--------|----------------|----------------|
| **Definition** | Examines code, design, or requirements *without execution*. | Validates system by *executing* it. |
| **Focus** | Prevention — catching errors early. | Detection — identifying defects that escaped earlier stages. |
| **Examples** | Reviews, inspections, walkthroughs, static code analysis. | Unit testing, integration testing, system testing, acceptance testing. |
| **Performed By** | Developers, reviewers, QA analysts. | Developers, testers, end-users. |
| **Objective** | Improve quality before coding. | Ensure software behaves correctly after coding. |

Both are **complementary** — effective testing involves both static and dynamic methods.

---

## 3. Objectives of Dynamic Testing

1. **Validate functionality** — confirm that all features work as per requirements.  
2. **Verify integration** — ensure components interact correctly.  
3. **Identify defects** that slipped through earlier stages.  
4. **Assess performance** and response under various loads.  
5. **Ensure reliability and stability** before deployment.  
6. **Evaluate user experience** by testing real scenarios.

---

## 4. Phases of Dynamic Testing

Dynamic testing generally occurs in **four major phases**, aligned with software development stages.

### 4.1 Unit Testing
- **Objective:** Verify individual units or functions.  
- **Performed by:** Developers (usually automated).  
- **Focus:** Internal logic correctness.  
- **Tools:** JUnit, NUnit, PyTest, TestNG.

**Example:**  
Check if a “Calculate Total” function correctly sums items in a cart, even with zero or negative inputs.

---

### 4.2 Integration Testing
- **Objective:** Verify that modules communicate properly.  
- **Focus:** Data flow and interaction between components.  
- **Types:**  
  - *Top-down:* Starts from main modules, replacing lower ones with stubs.  
  - *Bottom-up:* Starts with lower modules, using drivers to simulate higher ones.  
  - *Hybrid (Sandwich):* Combines both.

**Example:**  
Verify that user registration data is stored correctly in the database and reflected on the profile page.

---

### 4.3 System Testing
- **Objective:** Validate the complete, integrated system against requirements.  
- **Performed by:** Independent QA team.  
- **Focus:** End-to-end workflows, security, performance, usability.  

**Example:**  
Test whether an online booking application allows users to search, book, and pay seamlessly.

---

### 4.4 Acceptance Testing
- **Objective:** Validate readiness for release and user satisfaction.  
- **Performed by:** End-users or clients.  
- **Types:**
  - *UAT (User Acceptance Testing)* — verifies business flow.
  - *Alpha Testing* — internal team validation before public release.
  - *Beta Testing* — external users test in real environments.

**Example:**  
A small group of customers tests an app’s usability before global rollout.

---

## 5. Dynamic Testing Techniques

### 5.1 White-Box Testing (Structural)
- Tests the **internal logic** of code.
- Requires knowledge of source code.
- Focus on paths, conditions, and loops.

**Common Techniques:**
- Statement coverage  
- Branch coverage  
- Path coverage  
- Condition coverage  

**Example:**  
Testing every `if` and `else` condition in a function.

---

### 5.2 Black-Box Testing (Functional)
- Tests **external behavior** without knowing internal structure.
- Based on inputs and expected outputs.
- Emphasizes user-level validation.

**Common Techniques:**
- Equivalence Partitioning  
- Boundary Value Analysis  
- Decision Table Testing  
- State Transition Testing  

**Example:**  
Verify login form behavior for valid and invalid credentials.

---

### 5.3 Grey-Box Testing
- Combines knowledge of both internal structure and external behavior.
- Useful in integration and system testing.
- Helps identify interface and data flow issues.

**Example:**  
Knowing the API structure, a tester validates both input validation and output correctness.

---

## 6. Key Concepts in Dynamic Testing

### 6.1 Test Case
A **documented scenario** describing how to test a specific functionality, including:
- Pre-conditions
- Test data
- Steps to execute
- Expected result
- Actual result

**Example:**
| Step | Action | Expected Result |
|------|--------|----------------|
| 1 | Enter valid credentials | User logs in successfully |
| 2 | Enter invalid credentials | Error message displayed |

---

### 6.2 Test Scenario
A **high-level description** of what needs to be tested.  
One scenario can cover multiple test cases.

**Example:**  
“Verify login functionality” → includes valid, invalid, empty field, and special character test cases.

---

### 6.3 Test Data
The **input values** used to execute test cases.  
It can be:
- Valid data (expected behavior)
- Invalid data (negative testing)
- Boundary data (edge values)

---

### 6.4 Test Environment
The **hardware, software, and configurations** where testing takes place.

**Example:**  
Browser: Chrome v120, OS: Windows 11, Backend: MySQL, API: v2.3

---

## 7. Entry and Exit Criteria

### 7.1 Entry Criteria
Conditions that must be met before starting testing.
- Requirements finalized and approved.  
- Test cases and environment ready.  
- Code unit tested and deployed to QA environment.

### 7.2 Exit Criteria
Conditions to be met before closing the testing phase.
- All test cases executed.  
- Critical defects resolved.  
- Test summary report prepared.  
- Customer approval (for acceptance testing).

---

## 8. Defect Life Cycle

Dynamic testing heavily relies on **defect management**.

| Stage | Description |
|-------|--------------|
| New | Tester logs a new defect. |
| Assigned | Assigned to developer for fixing. |
| Open | Developer works on the fix. |
| Fixed | Developer completes changes. |
| Retest | Tester validates the fix. |
| Closed | Defect confirmed resolved. |
| Reopened | If issue persists after retest. |

**Goal:** Maintain traceability of every defect until closure.

---

## 9. Regression Testing

Whenever new changes are introduced, testers must verify that **existing functionality remains intact**.  
This is called **Regression Testing**.

**Example:**  
After updating a login module, ensure other pages (like registration and profile) still work properly.

Regression testing is often automated using tools like:
- Selenium  
- Cypress  
- Playwright  
- JUnit (for backend)

---

## 10. Test Automation in Dynamic Testing

Automation accelerates regression and functional testing by reusing scripts.  
However, automation is **not a replacement** for human exploratory testing.

### Benefits:
- Reduces repetitive work  
- Increases test coverage  
- Enables faster feedback  

### Limitations:
- High setup cost  
- Not suitable for UI instability or frequent changes  

**Best Practice:** Automate stable, repetitive, and high-value scenarios.

---

## 11. Dynamic Testing Metrics

| Metric | Formula | Purpose |
|--------|----------|---------|
| Test Execution Coverage | (Executed Test Cases / Total Test Cases) × 100 | Shows progress |
| Defect Density | (Defects Found / KLOC or Function Points) | Quality measure |
| Test Pass Percentage | (Passed Tests / Executed Tests) × 100 | Stability indicator |
| Defect Leakage | (Defects found post-release / total defects) × 100 | Reveals testing efficiency |

---

## 12. Challenges in Dynamic Testing

1. **Environment instability** — mismatched versions or dependencies.  
2. **Incomplete requirements** — unclear expectations.  
3. **Poor data management** — lack of realistic datasets.  
4. **Time constraints** — pressure to meet release deadlines.  
5. **Automation failures** — brittle scripts due to UI changes.  
6. **Complex integration points** — third-party APIs or microservices.  

**Mitigation:** Strong planning, realistic schedules, version control, and collaborative testing culture.

---

## 13. Best Practices for Dynamic Testing

- Start testing early — shift-left approach.  
- Maintain versioned test cases and data.  
- Use real-world scenarios.  
- Automate repetitive flows but always explore manually.  
- Keep clear communication between Dev, QA, and Product.  
- Track and learn from every defect.

---

## 14. Summary

| Key Concept | Description |
|--------------|--------------|
| **Dynamic Testing** | Execution-based validation of system behavior. |
| **Types** | Unit, Integration, System, Acceptance. |
| **Techniques** | White-box, Black-box, Grey-box. |
| **Artifacts** | Test cases, scenarios, data, environment. |
| **Goal** | Verify correctness and stability of software through execution. |
| **Value** | Demonstrates real-world quality, ensures user satisfaction. |

---

## 15. Review Questions

1. What distinguishes dynamic testing from static testing?  
2. Name four major levels of dynamic testing.  
3. How does regression testing differ from retesting?  
4. What are white-box and black-box testing techniques used for?  
5. What is a test case vs. test scenario?  
6. Explain one real-world example of integration testing.  
7. How can automation complement dynamic testing?  
8. What are three common dynamic testing metrics?

---

**End of Chapter 9 — Dynamic Testing Fundamentals**
