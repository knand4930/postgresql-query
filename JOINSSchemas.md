# PostgreSQL Joins & Schemas

## PostgreSQL Joins

### 1. LEFT JOIN
Retrieves all records from the left table and the matching records from the right table. If no match is found, NULL is returned for columns from the right table.
```sql
SELECT a.id, a.name, b.order_id
FROM customers a
LEFT JOIN orders b ON a.id = b.customer_id;
```

### 2. INNER JOIN
Returns only the matching records from both tables.
```sql
SELECT a.id, a.name, b.order_id
FROM customers a
INNER JOIN orders b ON a.id = b.customer_id;
```

### 3. FULL OUTER JOIN
Returns all records from both tables, with NULLs where there is no match.
```sql
SELECT a.id, a.name, b.order_id
FROM customers a
FULL OUTER JOIN orders b ON a.id = b.customer_id;
```

### 4. SELF JOIN
Joins a table with itself to compare records within the same table.
```sql
SELECT e1.id, e1.name, e2.name AS manager_name
FROM employees e1
LEFT JOIN employees e2 ON e1.manager_id = e2.id;
```

## PostgreSQL Schemas

### 1. CREATE SCHEMA
Creates a new schema to organize database objects.
```sql
CREATE SCHEMA sales;
```

### 2. DROP SCHEMA
Deletes an existing schema along with its objects.
```sql
DROP SCHEMA sales CASCADE;
```

### 3. ALTER SCHEMA
Renames an existing schema.
```sql
ALTER SCHEMA sales RENAME TO marketing;
```

---
These queries demonstrate how to effectively use joins and schemas in PostgreSQL to structure and manage your data efficiently.
