# PostgreSQL Control Flow & Transactions

## Control Flow Statements

### 1. IF Statement
```sql
DO $$
BEGIN
    IF 10 > 5 THEN
        RAISE NOTICE '10 is greater than 5';
    END IF;
END $$;
```
**Explanation**: Checks if a condition is met and executes the block if true.

### 2. CASE Statement
```sql
SELECT
    id,
    name,
    CASE
        WHEN age < 18 THEN 'Minor'
        WHEN age BETWEEN 18 AND 60 THEN 'Adult'
        ELSE 'Senior'
    END AS category
FROM users;
```
**Explanation**: Evaluates conditions and returns values based on matching cases.

### 3. Loop Statement
```sql
DO $$
DECLARE i INT := 1;
BEGIN
    LOOP
        EXIT WHEN i > 5;
        RAISE NOTICE 'Value: %', i;
        i := i + 1;
    END LOOP;
END $$;
```
**Explanation**: Runs a loop until explicitly exited.

### 4. While Loop
```sql
DO $$
DECLARE i INT := 1;
BEGIN
    WHILE i <= 5 LOOP
        RAISE NOTICE 'Counter: %', i;
        i := i + 1;
    END LOOP;
END $$;
```
**Explanation**: Loops while a condition holds true.

### 5. Exit Statement
```sql
DO $$
DECLARE i INT := 1;
BEGIN
    LOOP
        EXIT WHEN i > 3;
        RAISE NOTICE 'Iteration: %', i;
        i := i + 1;
    END LOOP;
END $$;
```
**Explanation**: Exits the loop when a condition is met.

### 6. Continue Statement
```sql
DO $$
DECLARE i INT := 0;
BEGIN
    LOOP
        i := i + 1;
        IF i = 3 THEN
            CONTINUE;
        END IF;
        RAISE NOTICE 'Processing: %', i;
        EXIT WHEN i >= 5;
    END LOOP;
END $$;
```
**Explanation**: Skips the current iteration and moves to the next.

---

## Transactions & Constraints

### 7. Transactions
```sql
BEGIN;
UPDATE users SET balance = balance - 100 WHERE id = 1;
UPDATE users SET balance = balance + 100 WHERE id = 2;
COMMIT;
```
**Explanation**: Ensures multiple SQL statements execute as a single unit.

### 8. COMMIT
```sql
BEGIN;
INSERT INTO orders (user_id, total) VALUES (1, 500);
COMMIT;
```
**Explanation**: Saves all changes made during the transaction.

### 9. Primary Key
```sql
CREATE TABLE customers (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL
);
```
**Explanation**: Ensures each row has a unique identifier.

### 10. Foreign Key
```sql
CREATE TABLE orders (
    id SERIAL PRIMARY KEY,
    customer_id INT REFERENCES customers(id)
);
```
**Explanation**: Establishes a relationship between tables.

### 11. CHECK Constraint
```sql
CREATE TABLE employees (
    id SERIAL PRIMARY KEY,
    age INT CHECK (age >= 18)
);
```
**Explanation**: Restricts values based on a condition.

### 12. UNIQUE Constraint
```sql
CREATE TABLE products (
    id SERIAL PRIMARY KEY,
    code VARCHAR(50) UNIQUE
);
```
**Explanation**: Ensures column values are unique.

### 13. NOT NULL Constraint
```sql
CREATE TABLE orders (
    id SERIAL PRIMARY KEY,
    order_date DATE NOT NULL
);
```
**Explanation**: Prevents null values in the column.

---

These queries demonstrate PostgreSQL control flow structures and constraints effectively.
