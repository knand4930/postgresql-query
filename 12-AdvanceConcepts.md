# PostgreSQL Advanced Concepts

## Dollar-Quoted String Constants
Dollar-quoted string constants allow including special characters or multiple quotes without escaping.
```sql
SELECT $$This is a 'quoted' string with a newline
Another line$$;
```

## Block Structure (PL/pgSQL)
PL/pgSQL supports block structures with BEGIN-END.
```sql
DO $$
BEGIN
    RAISE NOTICE 'Hello, PostgreSQL!';
END $$;
```

## Variables in PL/pgSQL
PL/pgSQL allows declaring variables inside functions or blocks.
```sql
DO $$
DECLARE message TEXT := 'Hello, PostgreSQL!';
BEGIN
    RAISE NOTICE '%', message;
END $$;
```

## Introduction to Stored Procedures
Stored procedures allow executing a sequence of SQL statements.
```sql
CREATE PROCEDURE add_employee(name TEXT, age INT)
LANGUAGE plpgsql
AS $$
BEGIN
    INSERT INTO employees (name, age) VALUES (name, age);
END $$;
```

## Trigger in PostgreSQL
Triggers automatically execute SQL statements before or after events.
```sql
CREATE OR REPLACE FUNCTION trigger_function()
RETURNS TRIGGER AS $$
BEGIN
    NEW.updated_at := now();
    RETURN NEW;
END $$ LANGUAGE plpgsql;
```

## CREATE TRIGGER
Creating a trigger that updates the `updated_at` column on row modifications.
```sql
CREATE TRIGGER update_timestamp
BEFORE UPDATE ON employees
FOR EACH ROW
EXECUTE FUNCTION trigger_function();
```

## DROP TRIGGER
Removing a trigger from a table.
```sql
DROP TRIGGER update_timestamp ON employees;
```

## Disabling a Trigger
Temporarily disable a trigger without dropping it.
```sql
ALTER TABLE employees DISABLE TRIGGER update_timestamp;
```

## Enabling a Trigger
Re-enable a previously disabled trigger.
```sql
ALTER TABLE employees ENABLE TRIGGER update_timestamp;
```

## CREATE INDEX
Creating an index to improve search performance.
```sql
CREATE INDEX employee_name_idx ON employees (name);
```

## List Indexes
Listing all indexes on a table.
```sql
SELECT indexname, indexdef FROM pg_indexes WHERE tablename = 'employees';
```

## UNIQUE Index
Creating a unique index to ensure column values are distinct.
```sql
CREATE UNIQUE INDEX unique_employee_email ON employees (email);
