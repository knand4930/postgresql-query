## PostgreSQL Roles & Permissions

### 1. CREATE ROLE
Creates a new role (user or group) in PostgreSQL.
```sql
CREATE ROLE user_readonly WITH LOGIN PASSWORD 'securepassword';
```

### 2. ALTER ROLE
Modifies an existing role's attributes.
```sql
ALTER ROLE user_readonly WITH SUPERUSER;
```

### 3. DROP ROLE
Deletes an existing role from the database.
```sql
DROP ROLE user_readonly;
```

### 4. GRANT
Assigns specific privileges to a role.
```sql
GRANT SELECT ON TABLE customers TO user_readonly;
```

### 5. REVOKE
Removes privileges from a role.
```sql
REVOKE SELECT ON TABLE customers FROM user_readonly;
```

### 6. Role Membership
Grants role membership to another role.
```sql
GRANT admin TO user_readonly;
```

---
These queries demonstrate how to effectively use joins, schemas, roles, and permissions in PostgreSQL to structure and manage your data efficiently.
