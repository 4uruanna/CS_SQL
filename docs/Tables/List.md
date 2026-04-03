[Home](../readme.md) / The basics / [Tables](../Tables.md) / List

# List

**MariaDB**
```SQL
SELECT table_name FROM information_schema.tables WHERE table_schema = 'database_name';
```

**PostgreSQL**
```SQL
SELECT table_schema, table_name FROM information_schema.tables;
```

**SQL Server**
```SQL
SELECT name FROM sys.tables;
```