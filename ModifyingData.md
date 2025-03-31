## Modifying Data

### 1. INSERT
Inserts a single row into a table.
```sql
INSERT INTO table_name (column1, column2) VALUES ('value1', 'value2');
```

### 2. Insert Multiple Values in Various Rows
Inserts multiple rows at once.
```sql
INSERT INTO table_name (column1, column2) VALUES ('value1', 'value2'), ('value3', 'value4');
```

### 3. UPDATE Statement
Modifies existing records in a table.
```sql
UPDATE table_name SET column1 = 'new_value' WHERE condition;
```

### 4. DELETE
Removes records from a table.
```sql
DELETE FROM table_name WHERE condition;
```

### 5. UPSERT (INSERT ON CONFLICT)
Inserts or updates a record depending on whether a conflict occurs.
```sql
INSERT INTO table_name (id, column1) VALUES (1, 'value') ON CONFLICT (id) DO UPDATE SET column1 = 'new_value';
```

## Conditionals

### 1. CASE
Performs conditional operations within queries.
```sql
SELECT column1, CASE WHEN condition THEN 'result1' ELSE 'result2' END FROM table_name;
```

### 2. COALESCE
Returns the first non-null value from a list.
```sql
SELECT COALESCE(column1, 'default_value') FROM table_name;
```

### 3. NULLIF() Function
Returns NULL if two values are equal; otherwise, returns the first value.
```sql
SELECT NULLIF(value1, value2);
```

### 4. CAST
Converts a value from one data type to another.
```sql
SELECT CAST(column1 AS INTEGER) FROM table_name;
```

