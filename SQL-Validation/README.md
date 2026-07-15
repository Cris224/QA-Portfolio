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
