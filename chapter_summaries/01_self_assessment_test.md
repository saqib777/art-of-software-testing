# Chapter 1 — A Self-Assessment Test

> *“If you think testing is simple, try writing test cases for the following problems.”*  
> — Glenford J. Myers, *The Art of Software Testing*

---

## 1. Purpose of the Chapter

The opening chapter of *The Art of Software Testing* sets the tone for the entire book by immediately putting the reader in the role of a tester.  
Before teaching theory, Myers challenges readers with **a self-assessment test** — a small set of programming problems for which one must design tests.  

This exercise reveals how deceptively hard it is to design comprehensive tests, and why *testing is a creative, disciplined skill rather than a checklist*.

---

## 2. The Self-Assessment Test (Classic Problems)

Below are the canonical problems presented by Myers.  
You don’t write the program — you design **test cases** that would effectively test the logic.

---

### 🧩 Problem 1 — The Triangle Program

> Write tests for a program that reads three integers (A, B, C), which are interpreted as the lengths of the sides of a triangle.  
> The program should print one of the following:
> - *Scalene triangle*  
> - *Isosceles triangle*  
> - *Equilateral triangle*  
> - *Not a triangle*

**Testing Objective:**  
Ensure the program correctly classifies all valid triangles and rejects invalid ones.

#### Key Test Scenarios

| Category | Example Inputs | Expected Output |
|-----------|----------------|-----------------|
| All sides equal | 3, 3, 3 | Equilateral |
| Two sides equal | 3, 3, 4 | Isosceles |
| All sides different | 4, 5, 6 | Scalene |
| Violates triangle inequality | 1, 2, 3 | Not a triangle |
| Zero or negative values | 0, 4, 5 / -3, 4, 5 | Not a triangle |
| Large numbers / boundary conditions | 10,000, 10,000, 10,000 | Equilateral |
| Floating vs integer inputs (if supported) | 3.5, 3.5, 5 | Isosceles |

**Testing Lessons:**  
Most testers initially forget cases where the triangle inequality fails (e.g., 1 + 2 = 3).  
This illustrates **incomplete testing due to human bias** — a core idea in the book.

---

### 🧩 Problem 2 — The Next Date Function

> Write test cases for a function that takes a date (day, month, year) and returns the next day’s date.

**Testing Objective:**  
Verify correctness for valid ranges and transitions across months, years, and leap years.

#### Key Test Scenarios

| Category | Example Input | Expected Output |
|-----------|----------------|-----------------|
| Regular day | 15/6/2024 | 16/6/2024 |
| End of month | 31/1/2024 | 1/2/2024 |
| End of 30-day month | 30/4/2024 | 1/5/2024 |
| End of February (non-leap) | 28/2/2023 | 1/3/2023 |
| Leap year February | 29/2/2024 | 1/3/2024 |
| End of year | 31/12/2024 | 1/1/2025 |
| Invalid date | 32/1/2024 | Error or invalid input |

**Testing Lessons:**  
Edge cases are everywhere — month transitions, year rollover, leap years.  
Good testers *anticipate boundaries and exceptions.*

---

### 🧩 Problem 3 — Commission Calculation

> A salesperson earns a commission based on total sales of locks, stocks, and barrels.

| Product | Unit Price |
|----------|-------------|
| Locks | $45 |
| Stocks | $30 |
| Barrels | $25 |

Rules:
- Sales are entered as quantities for each item.  
- Total commission = 10% of sales up to $1000, + 15% on the next $800, + 20% beyond $1800.  
- Invalid input if any quantity < 0 or if any quantity > 70 (inventory cap).

#### Key Test Scenarios

| Category | Example Input (locks, stocks, barrels) | Expected Behavior |
|-----------|----------------------------------------|-------------------|
| Normal sale | 10, 10, 10 | Valid, calculate commission |
| Upper boundary valid | 70, 70, 70 | Valid, max commission |
| Exceeding limit | 71, 10, 10 | Invalid |
| Negative input | -1, 5, 5 | Invalid |
| Boundary at $1000 | Sale = exactly $1000 | Switch to next commission tier |
| Boundary at $1800 | Sale = exactly $1800 | Switch to next tier |
| Mixed product entries | Varying lock-stock-barrel combos | Correct totals |

**Testing Lessons:**  
Teaches **boundary value analysis** and **equivalence partitioning**, foundational design techniques introduced formally in Chapter 4.

---

## 3. What This Chapter Demonstrates

| Concept | Description |
|----------|--------------|
| **Testing ≠ Proving Correctness** | Testing aims to *find errors*, not to prove there are none. |
| **Human Bias** | Programmers tend to design tests to confirm their code works. Testers must think oppositely. |
| **Exhaustive Testing is Impossible** | Even simple programs have thousands of paths; testers must prioritize intelligently. |
| **Thinking Like a Tester** | Good test design anticipates edge cases, invalid inputs, and unintended behavior. |

---

## 4. Practical Exercises

1. Design 10 more test cases for the triangle problem focusing on **invalid and borderline conditions**.  
2. Write your own small algorithm (like grade calculation or password validation) and attempt to test it *before coding*.  
3. Compare your test set with a peer’s — what cases did you both miss?

---

## 5. Key Takeaways

- Testing starts **before** coding; it is part of design thinking.  
- The *simplest-looking programs* often have the most subtle test requirements.  
- Understanding boundaries, equivalence, and invalid cases is essential.  
- **Purpose of this chapter:** awaken the tester mindset — *skeptical, methodical, curious.*

---

### 🧾 Summary Quote

> *“Testing is the process of executing a program with the intent of finding errors.”*  
> — Glenford J. Myers

---

**End of Chapter 1 — Self-Assessment Test**
