[Home](../readme.md) / The basics / [Databases](../Databases.md) / List

# List

> Note: Don't worry if you see databases that don't belong to you. Some databases are created by your engine to ensure it runs properly.

**MariaDB & SQL Server**
```SQL
SELECT schema_name FROM information_schema.schemata;
```

**PostgreSQL** 
```SQL
SELECT datname FROM pg_database WHERE datistemplate = false;
```