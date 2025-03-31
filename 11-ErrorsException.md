# PostgreSQL Error Handling and Exception Handling

## 1. Errors & Exception Handling in PostgreSQL
PostgreSQL provides robust error handling mechanisms that help catch and handle errors gracefully.

### Example: Basic Exception Handling
```sql
DO $$
BEGIN
    PERFORM 1 / 0;  -- Division by zero error
EXCEPTION
    WHEN division_by_zero THEN
        RAISE NOTICE 'Cannot divide by zero';
END $$;
```
**Explanation:** Catches a division by zero error and displays a notice.

## 2. PostgreSQL - Errors and Messages
PostgreSQL logs errors and messages at different levels, such as `DEBUG`, `INFO`, `NOTICE`, `WARNING`, and `ERROR`.

### Example: Raising a Custom Error Message
```sql
RAISE EXCEPTION 'Invalid operation detected' USING HINT = 'Check input values';
```
**Explanation:** Raises an error with a custom message and hint.

## 3. Exception Handling in PL/pgSQL
PL/pgSQL allows exception handling using the `EXCEPTION` block.

### Example: Handling Foreign Key Violation
```sql
BEGIN
    INSERT INTO orders (id, user_id) VALUES (1, 999);  -- Assuming 999 does not exist in users table
EXCEPTION
    WHEN foreign_key_violation THEN
        RAISE NOTICE 'Foreign key constraint violated';
END;
```
**Explanation:** Catches foreign key violations and displays a notice.

## 4. PostgreSQL - ASSERT Statement
The `ASSERT` statement is used for debugging to check conditions during execution.

### Example: Using ASSERT
```sql
DO $$
BEGIN
    ASSERT 2 + 2 = 4, 'Math is broken!';
END $$;
```
**Explanation:** Ensures the condition holds; otherwise, it raises an assertion failure.

---
### Summary:
- `RAISE EXCEPTION`: Raises custom error messages.
- `EXCEPTION` block: Handles specific errors like division by zero or foreign key violations.
- `ASSERT`: Debugging tool to ensure conditions hold.

Use these techniques to handle errors effectively in PostgreSQL.
