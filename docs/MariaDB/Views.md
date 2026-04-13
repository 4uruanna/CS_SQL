[Home](../../readme.md) / MariaDB / Views

# Views

[⛓️ [mariadb.com] "_Views_"](https://mariadb.com/docs/server/server-usage/tables/mariadb-views-guide-1)

Views are virtual tables based on the result set of an SQL statement.

A view always displays data in real time and does not copy it (only the view definition is stored).

## Summary

1. [Create](#create)
2. [Delete](#delete)
3. [Select](#select)
4. [Update](#update)

## <div id="create">1. Create</div>

[⛓️ [mariadb.com] "_Create view_"](https://mariadb.com/docs/server/server-usage/views/create-view)

```SQL
CREATE VIEW {{view_name}}
AS SELECT {{column_a}}, {{column_b}}, ...
FROM {{table_name}}
WHERE {{CONDITION}};
```

## <div id="delete">2. Delete</div>

```SQL
DROP VIEW {{view_name}};
```

## <div id="select">3. Select</div>

```SQL
SELECT * FROM {{view_name}};
```

## <div id="update">Update</div>

```SQL
CREATE OR REPLACE VIEW {{view_name}}
AS SELECT {{column_a}}, {{column_b}}, ...
FROM {{table_name}}
WHERE {{condition}};
```