[Home](../../readme.md) / MariaDB / Tables

# Tables

Now that you have created your first database you need to understand how table manipulation works.

## Summary

1. [Clone](#clone)
2. [Create](#create)
3. [Drop](#drop)
4. [List](#list)
5. [Truncate](#truncate)
6. [Alter](#alter)
    1. [Column](#alter-column)
    2. [Constraint](#alter-constraint)
    3. [Default](#alter-default)

## <div id="clone">1. Clone</div>

[⛓️ [mariadb.com] "_Create table_"](https://mariadb.com/docs/server/server-usage/tables/create-table)

```SQL
CREATE TABLE {{clone_table_name}} LIKE {{source_table_name}};
```

## <div id="create">2. Create</div>

[⛓️ [mariadb.com] "_Create table_"](https://mariadb.com/docs/server/server-usage/tables/create-table)

```SQL
CREATE TABLE table_name (
    column_name_a {{datatype}} {{constraint}},
    column_name_b {{datatype}} {{constraint}},
    column_name_c {{datatype}} {{constraint}},
    ... 
);
```

## <div id="drop">3. Drop</div>

[⛓️ [mariadb.com] "_Drop table_"](https://mariadb.com/docs/server/server-usage/tables/drop-table)

```SQL
DROP TABLE {{table_name}};
```

## <div id="list">4. List</div>

[⛓️ [mariadb.com] "_Information Schema_"](https://mariadb.com/docs/server/reference/system-tables/information-schema)

```SQL
SELECT table_name FROM information_schema.tables WHERE table_schema = '{{database_name}}';
```

> `information_schema` is a standard-compliant database that exposes metadata about the server.

## <div id="truncate">5. Truncate</div>

[⛓️ [mariadb.com] "_Truncate table_"](https://mariadb.com/docs/server/reference/sql-statements/table-statements/truncate-table)

```SQL
TRUNCATE TABLE {{table_name}};
```

## <div id="alter">6. Alter</div>

[⛓️ [mariadb.com] "_Alter table_"](https://mariadb.com/docs/server/reference/sql-statements/data-definition/alter/alter-table)

### <div id="alter-column">6.1. Column</div>

```SQL
-- Add
ALTER TABLE {{table_name}} ADD COLUMN {{datatype}} {{constraint}};
-- Drop
ALTER TABLE {{table_name}} DROP COLUMN {{column_name}};
-- Rename
ALTER TABLE {{table_name}} RENAME COLUMN {{old_column_name}} TO {{new_column_name}};
-- Update
ALTER TABLE {{table_name}} MODIFY {{column_name}} {{datatype}} {{constraint}};
```

### <div id="alter-constraint">6.2. Constraint</div>

```SQL
-- Add
ALTER TABLE {{table_name}} ADD CONSTRAINT {{constraint_name}} {{constraint}};
-- Drop
ALTER TABLE {{table_name}} DROP {{CONSTRAINT}} constraint_name;
```

### <div id="alter-default">6.3. Default</div>

```SQL
-- Add
ALTER TABLE {{table_name}} ALTER COLUMN {{column_name}} SET DEFAULT '{{default_value}}';
-- Drop
ALTER TABLE {{table_name}} ALTER COLUMN {{column_name}} DROP DEFAULT;
```
