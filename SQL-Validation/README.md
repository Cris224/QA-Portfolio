# Database Integrity & SQL Data Validation Showcase
**Author:** Cristofer Lorenzana  
**Focus:** Backend Quality Control & Data Verification  

This document outlines the hypothetical database validation strategies and exact SQL queries I utilize to verify data integrity following front-end user actions.

---

## Scenario 1: User Registration Data Verification
**UI Action:** A user fills out the sign-up form on the website with a Name, Email, and Password, and clicks "Register". The UI displays a "Registration Successful" message.

**QA Objective:** Verify that the data was written to the backend database perfectly without corruption, data truncation, or missing mandatory fields.

### The SQL Verification Query:
```sql
SELECT user_id, name, email, password_hash, status, created_at
  FROM users
  WHERE email = 'newuser@example.com'; 
```
---

## Scenario 2: E-Commerce Order Placement & Inventory Deduction
**UI Action:** A logged-in user adds 2 items of a specific product to their shopping cart and completes a checkout.

**QA Objective:** Verify that the system accurately logs the transaction details across separate relational tables and properly deducts stock from the inventory table.
### The SQL Verification Query:
```sql
SELECT o.order_id, o.user_id, oi.product_id, oi.quantity, p.stock_quantity
  FROM orders o
    JOIN order_items oi ON o.order_id = oi.order_id
    JOIN products p ON oi.product_id = p.product_id
  WHERE o.user_id = 10452
    ORDER BY o.created_at DESC
      LIMIT 1;
```
