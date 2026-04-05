[Home](../../readme.md) / The basics / [Joins](../Joins.md) / Inner

# Full

**PostgreSQL & SQL Server**
```SQL
SELECT column_table_a, column_table_b, ...
FROM table_a
FULL JOIN table_a ON table_a.id = table_b.id;
```

**MariaDB**
```SQL
SELECT * FROM table_a LEFT JOIN table_b ON table_a.id = table_b.id
UNION
SELECT * FROM table_a RIGHT JOIN table_b ON table_a.id = table_b.id;
```