[Home](../readme.md) / The basics / Joins

# Query customization

## Case

Customize the output of a column using a switch/case statement type.

If no condition matches, it will return `NULL`.

```SQL
SELECT column_a
CASE
    WHEN column_a = 'Alice' THEN 1
    WHEN column_a = 'Bob' THEN 2
    ELSE 3
END AS column_b
FROM table_name;
```

## Distinct
Remove duplicates. This operation can be combined with certain [aggregate functions](./Resources/Functions/Aggregate.md), such as `COUNT`.

```SQL
SELECT column_a, DISTINCT column_b FROM table_name;
SELECT COUNT(DISTINCT column_a) FROM table_name; 
```

## Group By

It is commonly used with [aggregate functions](./Resources/Functions/Aggregate.md) (such as `COUNT`, `MAX` ...).

```SQL
SELECT column_a, COUNT(column_b), MAX(column_c) FROM table_name
WHERE {{CONDITION}}
GROUP BY column_a;
```

## Having

Filters the results of a `GROUP BY`.
```SQL
SELECT COUNT(column_a), column_b
FROM table_name
WHERE {{CONDITION}}
GROUP BY column_b
HAVING COUNT(column_a) > 100;
```

## Limit & Offset

This allows you to create a pagination query.

**MariaDB & PostgreSQL**
```SQL
SELECT column_a, column_b, ...
FROM table_name
WHERE {{CONDITION}}
LIMIT 5
OFFSET 15
```

**SQL Server**
```SQL
SELECT TOP 5 column_a, column_b, ...
FROM table_name
WHERE {{CONDITION}}
OFFSET 15 ROWS
```

## ORDER BY

Sort the selected data by one or more columns. In ascending (`ASC`)  or descending (`DESC`) order.

```SQL
SELECT column_a, column_b, ...
FROM table_name
WHERE {{CONDITION}}
ORDER BY column_a ASC, column_b DESC;
```

## UNION & UNION ALL

Combine results from multiple `SELECT` (`UNION` will remove duplicates, unlike `UNION ALL`).

Each `SELECT` statement must have the same number of columns, be in the same order, and have the same data types.

```SQL
SELECT column_name FROM Customers
UNION
SELECT column_name FROM Suppliers
```

[← Joins](./Joins.md) ◎ [Transactions →](./Transactions.md)