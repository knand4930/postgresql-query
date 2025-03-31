# PostgreSQL Conditionals and Functions

PostgreSQL provides powerful conditional expressions and functions to enhance query capabilities. Below are some essential ones:

## 1. CASE Statement
The `CASE` statement allows conditional logic within SQL queries.

### Example:
```sql
SELECT id, name, 
    CASE 
        WHEN salary > 50000 THEN 'High'
        WHEN salary BETWEEN 30000 AND 50000 THEN 'Medium'
        ELSE 'Low'
    END AS salary_category
FROM employees;
```
**Explanation:** This query classifies employees' salaries into 'High', 'Medium', or 'Low' based on the amount.

---

## 2. COALESCE Function
The `COALESCE` function returns the first non-null value from a list of provided expressions.

### Example:
```sql
SELECT id, name, COALESCE(phone, 'No Phone Available') AS contact_info
FROM customers;
```
**Explanation:** If the `phone` field is `NULL`, it is replaced with 'No Phone Available'.

---

## 3. NULLIF() Function
The `NULLIF()` function returns `NULL` if two provided values are equal; otherwise, it returns the first value.

### Example:
```sql
SELECT NULLIF(100, 100) AS result; -- Returns NULL
SELECT NULLIF(100, 50) AS result; -- Returns 100
```
**Explanation:** If both values match, `NULLIF()` returns `NULL`; otherwise, it returns the first value.

---

## 4. CAST Function
The `CAST` function converts a value from one data type to another.

### Example:
```sql
SELECT '123'::INTEGER AS converted_value; -- Alternative syntax
SELECT CAST('123' AS INTEGER) AS converted_value;
```
**Explanation:** Converts the string `'123'` into an integer.

---

These functions and expressions provide greater flexibility in handling data within PostgreSQL queries.

