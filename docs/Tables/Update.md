[Home](../../readme.md) / The basics / [Tables](../Tables.md) /  Update

# Update

## Column

Add:
```SQL
ALTER TABLE table_name ADD COLUMN column_name {{DATATYPE}};
```

Remove:
```SQL
ALTER TABLE table_name DROP COLUMN column_name;
```

### Rename column

**MariaDB & PostgreSQL**
```SQL
ALTER TABLE table_name RENAME COLUMN old_name TO new_name;
```

**SQL Server**
```SQL
EXEC sp_rename 'table_name.old_name', 'new_name', 'COLUMN';
```

## Update column

**MariaDB & SQL Server**
```SQL
ALTER TABLE table_name MODIFY column_name {{DATATYPE}} {{CONSTRAINT}};
```

**PostgreSQL**
```SQL
ALTER TABLE table_name ALTER COLUMN column_name TYPE {{DATATYPE}};
```

### ✶ ADD CONSTRAINT ✶

```SQL
ALTER TABLE table_name ADD CONSTRAINT constraint_name {{CONSTRAINT}};
```

### ✶ REMOVE CONSTRAINT ✶

**PostgreSQL & SQL Server**
```SQL
ALTER TABLE table_name DROP CONSTRAINT constraint_name;
```

**MariaDB**
```SQL
ALTER TABLE ma_table DROP {{CONSTRAINT}} constraint_name;
```

### ✶ ADD DEFAULT ✶

**MariaDB & PostgreSQL**
```SQL
ALTER TABLE table_name ALTER COLUMN column_name SET DEFAULT 'DEFAULT DATA';
```

**SQL Server**
```SQL
ALTER TABLE table_name ADD CONSTRAINT constraint_name DEFAULT 'DEFAULT DATA' FOR column_name;
```

### ✶ REMOVE DEFAULT ✶

**MariaDB & PostgreSQL**
```SQL
ALTER TABLE table_name ALTER COLUMN column_name DROP DEFAULT;
```

**SQL Server**
```SQL
ALTER TABLE table_name DROP CONSTRAINT constraint_name;
```

### ✶ ADD INDEX ✶

```SQL
CREATE INDEX index_name ON table_name(column_a, column_b, ...);
```

### ✶ REMOVE INDEX ✶

**MariaDB & SQL Server**
```SQL
DROP INDEX index_name ON table_name;
```

**PostgreSQL**
```SQL
DROP INDEX index_name;
```
