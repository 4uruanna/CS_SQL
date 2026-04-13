[Home](../../readme.md) / MariaDB / Stored procedures

# Stored procedures

[⛓️ [mariadb.com] "_Stored procedures_"](https://mariadb.com/docs/server/server-usage/stored-routines/stored-procedures)

They allow you to:
- Reuse the query across multiple applications, which also makes maintenance easier
- Improve performance (they are precompiled and therefore execute faster)
- Protect against direct access to tables

## Summary

1. [Create](#create)
2. [Delete](#delete)
3. [Execute](#execute)

## <div id="create">1. Create</div>

```SQL
CREATE PROCEDURE {{procedure_name}}
    @{{param_a}} {{datatype}},
    @{{param_b}} {{datatype}},
    @{{param_c}} {{datatype}},
    ...
AS BEGIN
    -- Statements to be executed
    UPDATE {{table_name}}
    SET {{column_a}} = @param_a
    WHERE {{column_b}} = @param_b;

    SELECT {{column_a}}, {{column_b}}, ...
    FROM {{table_name}}
    WHERE {{column_b}} = @param_b;

    SELECT {{column_a}}, {{column_b}}, ...
    FROM {{table_name}}
    WHERE {{column_c}} = @param_c;
    -- End of statement
END;
```

## <div id="delete">2. Delete</div>

```SQL
DROP PROCEDURE {{procedure_name}};
```

## <div id="execute">3. Excecute</div>

```SQL
EXEC {{procedure_name}}
    @{{param_a}} = '{{value_a}}',
    @{{param_b}} = '{{value_b}}',
    @{{param_c}} = '{{value_c}}';
```
