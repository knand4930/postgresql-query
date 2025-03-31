## Querying Tables

### 1. SELECT
Retrieves data from a table.
```sql
SELECT * FROM table_name;
```

### 2. ORDER BY Clause
Sorts the result set.
```sql
SELECT * FROM table_name ORDER BY column_name ASC;
```

### 3. WHERE Clause
Filters records based on a condition.
```sql
SELECT * FROM table_name WHERE column_name = 'value';
```

### 4. FETCH Clause
Limits the number of rows returned.
```sql
SELECT * FROM table_name FETCH FIRST 10 ROWS ONLY;
```

### 5. IN Operator
Filters records matching multiple values.
```sql
SELECT * FROM table_name WHERE column_name IN ('value1', 'value2');
```

### 6. HAVING Clause
Filters grouped records based on a condition.
```sql
SELECT column_name, COUNT(*) FROM table_name GROUP BY column_name HAVING COUNT(*) > 5;
```

### 7. GROUP BY Clause
Groups records by one or more columns.
```sql
SELECT column_name, COUNT(*) FROM table_name GROUP BY column_name;
```

### 8. LIKE Operator
Searches for a pattern in a column.
```sql
SELECT * FROM table_name WHERE column_name LIKE 'pattern%';
```

### 9. BETWEEN Operator
Filters records within a range.
```sql
SELECT * FROM table_name WHERE column_name BETWEEN value1 AND value2;
```

