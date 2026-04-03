[Home](../../readme.md) / The basics / [Tables](../Tables.md) / Clone

# Clone

**MariaDB**
```SQL
CREATE TABLE table_clone LIKE table_source;
INSERT INTO table_clone SELECT * FROM table_source;
```

**PostgreSQL**
```SQL
CREATE TABLE table_clone (LIKE table_source INCLUDING ALL);
INSERT INTO table_clone SELECT * FROM table_source;
```

**SQL Server**
```SQL
SELECT * INTO table_clone FROM table_source;
```