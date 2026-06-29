# Test Plan: automationexercise.com. Functional Verification
**Author:** Cristofer Lorenzana  
**Date:** June 2026  

---

## 1. Introduction & Objective
The objective of this testing cycle is to perform comprehensive functional and exploratory UI testing on the core customer-facing features of automationexercise.com. The goal is to identify defects, ensure user flow consistency, and verify that the application behaves reliably under normal and edge-case conditions.

## 2. Scope of Testing
### In-Scope (What will be tested):
* **User Authentication:** Login, logout, and password error handling.
* **Search Functionality:** Keyword searching, filtering, and empty/null search states.
* **Core User Flow:** [Example: Product selection, adding items to the cart, modifying cart quantities, and proceeding to checkout].
* **Cross-Browser Compatibility:** UI rendering and functional behavior on Google Chrome and Mozilla Firefox.

### Out-of-Scope (What will NOT be tested):
* Backend database migrations (tested separately).
* Third-party payment gateway processing (simulated/mocked only).
* Performance and load testing under high traffic stress.

## 3. Testing Methodology & Techniques
We will apply standard black-box testing methodologies learned through my ISTQB foundational training:
* **Equivalence Partitioning & Boundary Value Analysis:** Applied to input fields (e.g., search bars, quantity adjusters) to ensure minimum, maximum, and invalid inputs fail gracefully.
* **Exploratory Testing:** Session-based testing to uncover unscripted edge cases and UI/UX anomalies.
* **Regression Testing:** Verifying that core existing functionality remains intact across multiple browser sessions.

## 4. Defect Reporting Criteria
All discovered anomalies will be documented in Jira. A high-quality defect report will include:
1. Unique Defect ID & Descriptive Summary
2. Preconditions & Environment Details (OS, Browser version)
3. Step-by-Step Reproduction Steps
4. Expected Result vs. Actual Result
5. Attachments (Screenshots/Screen recordings if applicable)

## 5. Pass/Fail Criteria
* **Pass:** The user flow functions exactly as expected without blocking deviations, data truncation, or unhandled application crashes.
* **Fail:** Any defect classified as High or Critical (e.g., app crashes, broken navigation links, unable to add items to cart) will cause the specific test suite to fail.
