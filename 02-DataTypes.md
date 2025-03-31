## Data Types

### 1. Boolean Data Type
Stores `TRUE`, `FALSE`, or `NULL` values.
```sql
CREATE TABLE example (is_active BOOLEAN);
```

### 2. CHAR Data Type
Fixed-length character data type.
```sql
CREATE TABLE example (code CHAR(5));
```

### 3. VARCHAR Data Type
Variable-length character data type.
```sql
CREATE TABLE example (name VARCHAR(50));
```

### 4. NUMERIC Data Type
Stores exact numbers with precision and scale.
```sql
CREATE TABLE example (price NUMERIC(10,2));
```

### 5. Date Data Type
Stores date values.
```sql
CREATE TABLE example (birth_date DATE);
```

### 6. TIME Data Type
Stores time values.
```sql
CREATE TABLE example (meeting_time TIME);
```

### 7. JSON Data Type
Stores JSON-formatted data.
```sql
CREATE TABLE example (data JSON);
```

### 8. CREATE DOMAIN
Defines a custom data type constraint.
```sql
CREATE DOMAIN positive_integer AS INT CHECK (VALUE > 0);
```

