# PostgreSQL Database Operations

## 1. Create a Database
Creates a new database.
```sql
CREATE DATABASE my_database;
```

## 2. Load a Database
Restores a database from a backup file.
```sh
psql -U username -d my_database -f backup.sql
```

## 3. Alter Database
Modifies database properties (e.g., owner, encoding).
```sql
ALTER DATABASE my_database OWNER TO new_owner;
```

## 4. Rename Database
Changes the database name.
```sql
ALTER DATABASE my_database RENAME TO new_database;
```

## 5. Show Databases
Lists all available databases.
```sql
\l
```

