[Home](../../readme.md) / MariaDB / Datas

# Datas

## Summary

1. [Clone](#clone)
2. [Delete](#delete)
3. [Insert](#insert)
4. [Select](#select)
5. [Update](#update)

## <div id="clone">1. Clone</div>

[⛓️ [mariadb.com] "_Insert select_"](https://mariadb.com/docs/server/reference/sql-statements/data-manipulation/inserting-loading-data/insert-select)

If you use the same names and the same order in both tables, you can also use a subquery to achieve this:
```SQL
INSERT INTO {{target_table_name}}
SELECT * FROM {{source_table_name}}
WHERE {{condition}};
```

Otherwiser:
```SQL
INSERT INTO {{target_table_name}} 
({{target_column_a}}, {{target_column_b}}, {{target_column_c}}, ...)
SELECT {{column_source_a}}, {{column_source_b}}, {{column_source_c}}, ...
FROM {{source_table_name}}
WHERE {{condition}};
```

## <div id="delete">2. Delete</div>

[⛓️ [mariadb.com] "_Delete table_"](https://mariadb.com/docs/server/server-usage/tables/drop-table)

```SQL
DELETE FROM {{table_name}} WHERE {{condition}}
```

## <div id="insert">3. Insert</div>

[⛓️ [mariadb.com] "_Insert table_"](https://mariadb.com/docs/server/reference/sql-statements/data-manipulation/inserting-loading-data/insert)

```SQL
INSERT INTO {{table_name}} ({{column_a}}, {{column_b}}, {{column_c}}, ...)
VALUES ({{a_value}}, {{b_value}}, {{c_value}}, ...);
```

## <div id="select">4. Select</div>

[⛓️ [mariadb.com] "_Select table_"](https://mariadb.com/docs/server/reference/sql-statements/data-manipulation/selecting-data/select)

```SQL
SELECT {{column_a}}, {{column_b}}, {{column_c}}, ...
FROM {{table_name}}
WHERE {{condition}};
```

## <div id="update">5. Update</div>

[⛓️ [mariadb.com] "_Update table_"](https://mariadb.com/docs/server/reference/sql-statements/data-manipulation/changing-deleting-data/update)

```SQL
UPDATE {{table_name}}
SET {{column_a}} = {{value_a}},
    {{column_b}} = {{value_b}},
    ...
WHERE {{condition}};
```
