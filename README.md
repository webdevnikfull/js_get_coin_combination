# 🪙 QA: Coin Combination - Algorithm Validation Suite

> ### A comprehensive unit testing suite built with **Jest** to validate a greedy algorithm designed for optimal coin dispensing.

This repository serves as a professional showcase of **Software Quality Assurance (QA)** practices, specifically focusing on mathematical and algorithmic verification. It demonstrates how to architect tests for the `getCoinCombination` function, ensuring it accurately calculates the smallest possible number of coins for a given amount.

---

## 🎯 System Under Test (SUT)

The `getCoinCombination` function accepts a non-negative integer representing a specific amount in `cents`[cite: 5]. It processes this input and returns an array representing the optimal (minimum) combination of coins required to match that exact amount[cite: 5].

**Data Structure (Output Array Mapping):**
- `coins[0]` = Number of pennies (1 cent)[cite: 5]
- `coins[1]` = Number of nickels (5 cents)[cite: 5]
- `coins[2]` = Number of dimes (10 cents)[cite: 5]
- `coins[3]` = Number of quarters (25 cents)[cite: 5]

**Expected Behavior Examples:**
- `getCoinCombination(1)` strictly equals `[1, 0, 0, 0]` (1 penny)[cite: 5]
- `getCoinCombination(6)` strictly equals `[1, 1, 0, 0]` (1 penny + 1 nickel)[cite: 5]
- `getCoinCombination(17)` strictly equals `[2, 1, 1, 0]` (2 pennies + 1 nickel + 1 dime)[cite: 5]
- `getCoinCombination(50)` strictly equals `[0, 0, 0, 2]` (2 quarters)[cite: 5]

---

## 🧪 QA Strategy & Test Design

To guarantee the algorithm handles all possible variations flawlessly, the test suite leverages **Jest expectations**[cite: 5] and targets the following scenarios:

| Testing Technique | Scenario Covered | QA Focus |
| :--- | :--- | :--- |
| **Boundary Value Analysis (BVA)** | Input is exactly `0` cents. | Validating the edge case where no coins should be dispensed (`[0, 0, 0, 0]`). |
| **Equivalence Class Partitioning** | Exact coin match (e.g., `25` cents). | Ensuring the algorithm doesn't overcomplicate and directly returns a single highest-value coin (`[0, 0, 0, 1]`). |
| **Equivalence Class Partitioning** | Complex combinations (e.g., `43` cents). | Verifying the "greedy" aspect of the algorithm—it must prioritize larger coins first before falling back to smaller ones. |
| **Data Type Validation** | Checking array length and element types. | Asserting that the output is exactly an array of 4 integers. |

---

## 🧰 Tech Stack

- **Environment:** Node.js
- **Language:** JavaScript (ES6+)
- **Testing Framework:** [Jest](https://jestjs.io/) 

---

## ⚙️ How to Run the Tests

To execute the test suite locally and review the assertions:

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/webdevnikfull/js_get_coin_combination.git](https://github.com/webdevnikfull/js_get_coin_combination.git)
   cd js_get_coin_combination
