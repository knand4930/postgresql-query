## Table Operations

### 1. CREATE TABLE
Creates a new table.
```sql
CREATE TABLE example (id SERIAL PRIMARY KEY, name VARCHAR(100));
```

### 2. SELECT INTO
Creates a new table from an existing table.
```sql
SELECT * INTO new_table FROM existing_table;
```

### 3. CREATE SEQUENCE
Creates a sequence for generating unique numbers.
```sql
CREATE SEQUENCE seq_example START 1;
```

### 4. ALTER TABLE
Modifies an existing table.
```sql
ALTER TABLE example ADD COLUMN age INT;
```

### 5. ADD COLUMN
Adds a new column to a table.
```sql
ALTER TABLE example ADD COLUMN email VARCHAR(255);
```

### 6. DROP COLUMN
Removes a column from a table.
```sql
ALTER TABLE example DROP COLUMN email;
```

### 7. Rename Table
Renames an existing table.
```sql
ALTER TABLE old_table RENAME TO new_table;
```

### 8. DROP TABLE
Deletes a table permanently.
```sql
DROP TABLE example;
```

### 9. TRUNCATE TABLE
Removes all records from a table but keeps the structure.
```sql
TRUNCATE TABLE example;
```

### 10. Copy a Table
Creates a copy of a table structure and data.
```sql
CREATE TABLE new_table AS TABLE existing_table;
```

### 11. Comparing Tables
Finds differences between two tables.
```sql
SELECT * FROM table1 EXCEPT SELECT * FROM table2;
```

### 12. Show Tables
Lists all tables in the current database.
```sql
\dt
```

