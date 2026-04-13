[Home](../../readme.md) / MariaDB / Query customizations

# Query customizations

## Summary

1. [Alias](#alias)
2. [Case](#case)
3. [Distinct](#distinct)
4. [Group By](#group-by)
5. [Having](#having)
6. [Limit & offset](#limit-and-offset)
7. [Order by](#order-by)
8. [Union](#union)

## <div id="alias">1. Alias</div>

[⛓️ [sql.sh] "_AS (alias)_"](https://sql.sh/cours/alias)

You can redefine columns and tables using the `AS` keyword.

```SQL
SELECT {{column_a}} AS {{column_a_alias}}
FROM {{table_a}} AS {{table_a_alias}}
INNER JOIN {{table_b}} AS {{table_b_alias}}
ON {{table_a_alias}}.column_c = tb.column_c;
```

## <div id="case">2. Case</div>

[⛓️ [mariadb.com] "_CASE statement_"](https://mariadb.com/docs/server/reference/sql-statements/programmatic-compound-statements/case-statement)

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

## <div id="distinct">3. Distinct</div>

[⛓️ [mariadb.com] "_Select_"](https://mariadb.com/docs/server/reference/sql-statements/data-manipulation/selecting-data/select#distinct)  
[⛓️ [mariadb.com] "_Count Distinct_"](https://mariadb.com/docs/server/reference/sql-functions/aggregate-functions/count-distinct)

Remove duplicates. This operation can be combined with certain [aggregate functions](./Resources/Functions/Aggregate.md), such as `COUNT`.

```SQL
SELECT {{column_a}}, DISTINCT {{column_b}} FROM {{table_name}};
SELECT COUNT(DISTINCT {{column_a}}) FROM {{table_name}}; 
```

## <div id="group-by">4. Group By</div>

[⛓️ [mariadb.com] "_Group by_"](https://mariadb.com/docs/server/reference/sql-statements/data-manipulation/selecting-data/group-by)

It is commonly used with [aggregate functions](./Resources/Functions/Aggregate.md) (such as `COUNT`, `MAX` ...).

```SQL
SELECT {{column_a}}, COUNT({{column_b}}), MAX({{column_c}}) FROM {{table_name}}
WHERE {{condition}}
GROUP BY {{column_a}};
```

## <div id="having">5. Having</div>

[⛓️ [sql.sh] "_Having_"](https://sql.sh/cours/having)

Filters the results of a `GROUP BY`.
```SQL
SELECT COUNT({{column_a}}), {{column_b}}
FROM {{table_name}}
WHERE {{condition}}
GROUP BY {{column_b}}
HAVING COUNT({{column_a}}) > 100;
```

## <div id="limit-and-offset">6. Limit & Offset</div>

[⛓️ [mariadb.com] "_Limit_"](https://mariadb.com/docs/server/reference/sql-statements/data-manipulation/selecting-data/limit)  
[⛓️ [mariadb.com] "_Select ... offset ... fetch_"](https://mariadb.com/docs/server/reference/sql-statements/data-manipulation/selecting-data/select-offset-fetch)

This allows you to create a pagination query.

```SQL
SELECT {{column_a}}, {{column_b}}, ...
FROM {{table_name}}
WHERE {{condition}}
LIMIT 5
OFFSET 15
```

## <div id="order-by">7. Order by</div>

[⛓️ [mariadb.com] "_Order by_"](https://mariadb.com/docs/server/reference/sql-statements/data-manipulation/selecting-data/order-by)

Sort the selected data by one or more columns. In ascending (`ASC`)  or descending (`DESC`) order.

```SQL
SELECT {{column_a}}, {{column_b}}, ...
FROM {{table_name}}
WHERE {{condition}}
ORDER BY {{column_a}} ASC, {{column_b}} DESC;
```

## <div id="union">8. Union</div>

[⛓️ [mariadb.com] "_Union_"](https://mariadb.com/docs/server/reference/sql-statements/data-manipulation/selecting-data/set-operations/union)

Combine results from multiple `SELECT` (`UNION` will remove duplicates, unlike `UNION ALL`).

Each `SELECT` statement must have the same number of columns, be in the same order, and have the same data types.

```SQL
SELECT {{column_a}}, {{column_b}}, ... 
FROM {{table_a}}
UNION
SELECT {{column_a}}, {{column_b}}, ...
FROM {{table_b}}
```