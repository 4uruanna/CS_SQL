[Home](../../readme.md) / The basics / [Tables](../Tables.md) / Clone

# Clone

**MariaDB**
```SQL
CREATE TABLE table_clone 
AS SELECT *
FROM table_source
WHERE {{CONDITION}};
```

**SQL Server & PostgreSQL**
```SQL
SELECT *
INTO table_clone
FROM table_source
WHERE {{CONDITION}};
```