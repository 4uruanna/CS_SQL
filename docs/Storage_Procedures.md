[Home](../readme.md) / The basics / Storage Procedures

# Storage Procedures

They allow you to:
- Reuse the query across multiple applications, which also makes maintenance easier
- Improve performance (they are precompiled and therefore execute faster)
- Protect against direct access to tables

## Create
```SQL
CREATE PROCEDURE procedure_a
    @param_a {{DATATYPE}},
    @param_b {{DATATYPE}},
    @param_c {{DATATYPE}},
    ...
AS BEGIN
    -- Statements to be executed
    UPDATE table_name
    SET column_a = @param_a
    WHERE column_b = @param_b;

    SELECT column_a, column_b, ...
    FROM table_name
    WHERE column_b = @param_b;

    SELECT column_a, column_b, ...
    FROM table_name
    WHERE column_c = @param_c;
    -- End of statement
END;
```

## Delete
```SQL
DROP PROCEDURE procedure_name;
```

## Excecute
```SQL
EXEC procedure_a
    @param_a = 'value_a',
    @param_b = 'value_b',
    @param_c = 'value_c';
```

[← Views](./Views.md) ◎ [ →](./.md)
