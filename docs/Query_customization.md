[Home](../readme.md) / The basics / Joins

# Query customization

## CASE

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

## GROUP BY

It is commonly used with [aggregate](./Resources/Functions/Aggregate.md) functions (such as `COUNT`, `MAX` ...).

```SQL
SELECT column_a, COUNT(column_b), MAX(column_c) FROM table_name
WHERE {{CONDITION}}
GROUP BY column_a;
```

## HAVING

Filters the results of a `GROUP BY`.
```SQL
SELECT COUNT(column_a), column_b
FROM table_name
WHERE {{CONDITION}}
GROUP BY column_b
HAVING COUNT(column_a) > 100;
```

## LIMIT & OFFSET

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


[← Joins](./Joins.md) ◎ [Transactions →](./Transactions.md)