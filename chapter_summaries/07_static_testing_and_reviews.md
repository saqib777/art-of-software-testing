# Chapter 7 — Static Testing and Reviews

> “The best defect is the one that never leaves the developer’s desk.”

---

## 1. Introduction

Static testing is a **non-execution-based approach** to testing software artifacts — that is, testing **without running the program**.  
It involves examining documents, code, requirements, and design for **errors, inconsistencies, or deviations** from standards before the software is executed.

Unlike dynamic testing, which validates behavior by **executing code**, static testing ensures **quality of thought** and **clarity of expression** in every artifact that precedes execution.

The essence of static testing is *prevention over detection*.

---

## 2. The Philosophy of Static Testing

In traditional development cycles, defects found late (during integration or system testing) cost **10 to 100 times more** to fix than those found early.  
Static testing serves as the **first line of defense**, identifying problems at their conceptual roots — requirements, design, and code readability.

Static testing enforces **discipline**, **collaboration**, and **early correction**, creating a culture of quality rather than a rush to deliver.

---

## 3. Objectives of Static Testing

1. Detect defects early (before execution).  
2. Improve consistency and completeness of requirements and design.  
3. Enforce adherence to coding and documentation standards.  
4. Identify ambiguous, missing, or conflicting information.  
5. Foster communication and shared understanding among team members.

---

## 4. Static Testing vs. Dynamic Testing

| Feature | Static Testing | Dynamic Testing |
|----------|----------------|-----------------|
| **Nature** | Preventive | Corrective |
| **Execution** | Code is not run | Code is executed |
| **Focus** | Process and artifacts | Product behavior |
| **Performed During** | Early phases (requirements, design, coding) | Later phases (system, acceptance) |
| **Defect Types Found** | Missing logic, syntax issues, requirement gaps | Functional errors, performance bugs |
| **Examples** | Reviews, walkthroughs, static analysis tools | Unit, integration, and system testing |

Both approaches are **complementary** — static testing enhances quality *before* code runs, while dynamic testing ensures quality *after* it runs.

---

## 5. Key Techniques of Static Testing

Static testing encompasses both **manual** and **automated** methods.

### 5.1 Manual Techniques
These involve **human examination** of artifacts for correctness and quality.

- **Informal Reviews**
- **Walkthroughs**
- **Technical Reviews**
- **Inspections**

### 5.2 Automated Techniques
These include **tool-based analysis** of code and documentation.

- Static Code Analysis  
- Code Metrics and Complexity Measurement  
- Linting and Style Checking  
- Security Vulnerability Scanning

---

## 6. Manual Review Techniques

### 6.1 Informal Review
A lightweight, unstructured process — typically a peer review or desk check.  
The goal is to provide **quick feedback** on drafts or early documents.

**Example:**  
A developer asks a peer to glance at a function implementation to confirm logic consistency or naming clarity.

**Pros:** Quick, flexible, low overhead.  
**Cons:** Depends heavily on reviewer skill; no formal record of findings.

---

### 6.2 Walkthrough

A **semi-formal** review led by the author of the document or code.  
The author “walks through” the material to explain logic, design, or assumptions to peers.

**Participants:**  
- Author (Presenter)  
- Reviewers (Team Members)  
- Recorder (Optional)

**Objective:**  
Gain collective understanding and uncover issues through discussion.

**Example:**  
A requirements analyst walks through a new user story specification with QA and developers to ensure clarity before sprint planning.

---

### 6.3 Technical Review

A **structured peer review** focused on technical correctness rather than presentation.  
It typically involves domain experts, architects, or senior engineers.

**Goal:**  
Ensure the artifact meets design and implementation standards and aligns with architecture or interface definitions.

**Example:**  
Before integration, the API design is technically reviewed to verify compliance with the service interface guidelines.

**Outcome:**  
Formal documentation of defects, improvement suggestions, and approval status.

---

### 6.4 Inspection

The most **formal and disciplined** static testing technique.

Defined originally by **Michael Fagan at IBM (1976)**, inspections follow a structured process to maximize defect detection efficiency.

#### Key Roles:
- **Moderator:** Manages the review session.
- **Author:** Creator of the artifact.
- **Reader:** Reads aloud sections for team understanding.
- **Recorder:** Documents issues and actions.
- **Reviewers:** Provide feedback based on checklists.

#### Inspection Process:

1. **Planning** — Define scope, participants, and objectives.  
2. **Overview Meeting** — The author explains context.  
3. **Preparation** — Reviewers study the artifact individually.  
4. **Inspection Meeting** — Defects are identified and recorded.  
5. **Rework** — The author corrects identified defects.  
6. **Follow-up** — Moderator ensures corrections are implemented.

**Typical Results:**
- Defect detection rates up to 80%.  
- Early removal of ambiguities and inconsistencies.  
- Reduced downstream testing effort.

---

## 7. Automated Static Analysis

With modern tools, static testing extends to **automated code analysis**.

### 7.1 Common Tools
- **SonarQube** — Measures code quality, maintainability, and security.  
- **ESLint / Pylint / Flake8** — Checks syntax and style compliance.  
- **Bandit** — Detects Python security issues.  
- **Checkstyle** — Ensures Java coding standards.

### 7.2 Typical Checks
| Category | Examples |
|-----------|-----------|
| **Syntax Errors** | Missing semicolons, unmatched brackets |
| **Security Vulnerabilities** | Hardcoded credentials, SQL injection |
| **Performance Risks** | Inefficient loops, redundant code |
| **Maintainability** | High cyclomatic complexity, long functions |
| **Style Compliance** | Naming conventions, spacing, comments |

### 7.3 Benefits
- Rapid, repeatable feedback.  
- Integration with CI/CD pipelines.  
- Quantitative metrics for technical debt.  
- Objective measurement of code health.

---

## 8. Advantages of Static Testing

1. **Early defect detection** — before runtime costs increase.  
2. **Improved documentation quality** — through peer visibility.  
3. **Reduced rework and debugging time.**  
4. **Enforced standards and consistency.**  
5. **Enhanced collaboration** among developers, testers, and analysts.  
6. **Knowledge sharing** across the team.

---

## 9. Limitations

1. **Cannot detect runtime issues** (performance, integration failures).  
2. **Requires human expertise** — subjective bias may occur.  
3. **Time-consuming** for large artifacts.  
4. **False positives** in automated tools.  
5. **Dependent on documentation quality.**

---

## 10. Example: Applying Static Testing

Consider a **requirement document** for an online banking login feature:

> “The system shall allow users to log in with valid credentials and display the welcome dashboard.”

**During static review:**
- Ambiguity: What defines “valid credentials”?  
- Missing requirement: What happens after 3 failed attempts?  
- Inconsistency: Is two-factor authentication mandatory?  

By catching these before implementation, the team prevents costly redesign and code rework.

---

## 11. The Human Element in Static Testing

Static testing is as much **social** as it is **technical**.  
It requires:
- Patience  
- Communication  
- Constructive criticism  
- Empathy for the author’s perspective

A review meeting is not a judgment; it is a **collaboration to enhance clarity and reliability**.

Teams that adopt review culture tend to produce:
- Fewer bugs
- More maintainable code
- Higher mutual respect between roles

---

## 12. Integrating Static Testing in Modern Workflows

In agile and DevOps pipelines, static testing manifests as:

- **Pull Request Reviews (GitHub/GitLab)**
- **Pre-commit Hooks**
- **Automated Static Code Analysis**
- **Documentation Linting**
- **Architecture Review Boards**

The blend of human and automated review ensures continuous quality.

---

## 13. Summary

| Aspect | Key Point |
|---------|------------|
| **Purpose** | Detect defects without executing code. |
| **Focus** | Clarity, completeness, and standard compliance. |
| **Methods** | Reviews, walkthroughs, inspections, static analysis. |
| **When Applied** | Throughout early development stages. |
| **Key Benefit** | Early prevention and cost reduction. |

Static testing embodies the principle of *"shift-left testing"* — finding issues as close to their source as possible.

---

## 14. Review Questions

1. What distinguishes static testing from dynamic testing?  
2. Describe the main steps of a formal inspection.  
3. How can static analysis tools complement human reviews?  
4. Why is documentation quality critical in static testing?  
5. Discuss how static testing aligns with agile development practices.  
6. What psychological aspects influence review effectiveness?

---

**End of Chapter 7 — Static Testing and Reviews**
