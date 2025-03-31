# PostgreSQL Operators and Functions

## PostgreSQL Operators

### UNION Operator
Combines the results of two queries and removes duplicates.
```sql
SELECT column_name FROM table1
UNION
SELECT column_name FROM table2;
```

### INTERSECT Operator
Returns only the common records between two queries.
```sql
SELECT column_name FROM table1
INTERSECT
SELECT column_name FROM table2;
```

### EXCEPT Operator
Returns records from the first query that are not in the second query.
```sql
SELECT column_name FROM table1
EXCEPT
SELECT column_name FROM table2;
```

### ANY Operator
Used to compare a value with any value in a subquery.
```sql
SELECT * FROM table1 WHERE column_name = ANY (SELECT column_name FROM table2);
```

### ALL Operator
Used to compare a value with all values in a subquery.
```sql
SELECT * FROM table1 WHERE column_name > ALL (SELECT column_name FROM table2);
```

### EXISTS Operator
Checks if a subquery returns any records.
```sql
SELECT * FROM table1 WHERE EXISTS (SELECT 1 FROM table2 WHERE table1.id = table2.id);
```

## PostgreSQL Functions

### CREATE FUNCTION Statement
Creates a user-defined function.
```sql
CREATE FUNCTION add_numbers(a INT, b INT) RETURNS INT AS $$
BEGIN
    RETURN a + b;
END;
$$ LANGUAGE plpgsql;
```

### Function Overloading
Defines multiple functions with the same name but different parameters.
```sql
CREATE FUNCTION add_numbers(a INT, b INT) RETURNS INT AS $$
BEGIN
    RETURN a + b;
END;
$$ LANGUAGE plpgsql;

CREATE FUNCTION add_numbers(a FLOAT, b FLOAT) RETURNS FLOAT AS $$
BEGIN
    RETURN a + b;
END;
$$ LANGUAGE plpgsql;
```

### DROP FUNCTION
Deletes a user-defined function.
```sql
DROP FUNCTION add_numbers(INT, INT);
```

### MAX() Function
Returns the maximum value from a column.
```sql
SELECT MAX(column_name) FROM table_name;
```

### MIN() Function
Returns the minimum value from a column.
```sql
SELECT MIN(column_name) FROM table_name;
```

### SUM() Function
Calculates the sum of a column.
```sql
SELECT SUM(column_name) FROM table_name;
```

### COUNT() Function
Counts the number of records.
```sql
SELECT COUNT(*) FROM table_name;
```

### EXTRACT() Function
Extracts a part (e.g., year, month) from a date.
```sql
SELECT EXTRACT(YEAR FROM current_date);
```

### REPLACE() Function
Replaces occurrences of a substring within a string.
```sql
SELECT REPLACE('Hello World', 'World', 'PostgreSQL');
