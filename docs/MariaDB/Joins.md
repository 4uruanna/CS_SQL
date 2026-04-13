[Home](../../readme.md) / MariaDB / Joins

# Joins

[⛓️ [mariadb.com] "_MariaDB Join Guide_"](https://mariadb.com/docs/server/mariadb-quickstart-guides/mariadb-join-guide)  
[⛓️ [mariadb.com] "_Join syntax_"](https://mariadb.com/docs/server/reference/sql-statements/data-manipulation/selecting-data/joins/join-syntax)

## Summary

1. [Inner](#inner)
2. [Left](#left)
3. [Right](#right)
4. [Full](#full)

## <div id="inner">1. Inner</div>

```SQL
SELECT {{column_a}}, {{column_b}}
FROM {{table_a}}
INNER JOIN {{table_b}} ON {{table_a}}.id = {{table_b}}.id;
```

## <div id="left">2. Left</div>

```SQL
SELECT {{column_a}}, {{column_b}}
FROM {{table_a}}
LEFT JOIN {{table_b}} ON {{table_a}}.id = {{table_b}}.id;
```

## <div id="right">3. Right</div>

```SQL
SELECT {{column_a}}, {{column_b}}
FROM {{table_a}}
RIGHT JOIN {{table_b}} ON {{table_a}}.id = {{table_b}}.id;
```

## <div id="full">4. Full</div>

```SQL
SELECT * FROM {{table_a}} LEFT JOIN {{table_b}} ON {{table_a}}.id = {{table_b}}.id
UNION
SELECT * FROM {{table_a}} RIGHT JOIN {{table_b}} ON {{table_a}}.id = {{table_b}}.id;
```
