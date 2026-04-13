[Home](../../readme.md) / MariaDB / Constraints

# Constraints

[⛓️  [mariadb.com] "_Constraint_"](https://mariadb.com/docs/server/reference/sql-statements/data-definition/constraint)

Constraints are rules for data in a table. They can be declared in `CREATE TABLE` and `ALTER TABLE`.

## Summary

1. [Auto Increment](#auto-increment)
2. [Check](#check)
3. [Default](#default)
4. [Foreign key](#foreign-key)
5. [Null & Not Null](#null-and-not-null)
6. [Primary key](#primary-key)
7. [Unique](#unique)

## <div id="auto-increment">1. Auto Increment</div>

[⛓️ [mariadb.com] "_AUTO_INCREMENT_"](https://mariadb.com/docs/server/reference/data-types/auto_increment)

_This should probably go in the “Data Types” section, but it my cheatsheet._

Automatically increments a value without having to manage it manually. Commonly used with `PRIMARY KEY`.

```SQL
CREATE TABLE {{table_name}} (
    {{column_a}} {{datatype}} AUTO_INCREMENT PRIMARY KEY;
)
```

## <div id="check">2. Check</div>

[⛓️ [mariadb.com] "_Check constraint_"](https://mariadb.com/docs/server/reference/sql-statements/data-definition/constraint#check-constraints)

Restricts the values accepted by one or multiple columns.

```SQL
CREATE TABLE {{table_name}}
(
    ...
    CONSTRAINT {{constraint_name}} CHECK ({{condition}})
);
```

## <div id="default">3. Default</div>

[⛓️ [mariadb.com] "_Default column option_"](https://mariadb.com/docs/server/server-usage/tables/create-table#default-column-option)

Define default value.
```SQL
CREATE TABLE {{table_name}}
(
    {{column_name}} {{datatype}} DEFAULT {{default_value}}
);
```

## <div id="foreign-key">4. Foreign key</div>

[⛓️ [mariadb.com] "_Foreign keys_"](https://mariadb.com/docs/server/ha-and-performance/optimization-and-tuning/optimization-and-indexes/foreign-keys)

Establishes a relationship with another table.
```SQL
CREATE TABLE {{table_name}}
(
    ...
    CONSTRAINT {{constraint_name}}
    FOREIGN KEY ({{column_a}})
    REFERENCES {{table_b}}({{column_b}})
)
```

## <div id="null-and-not-null">5. Null & Not Null</div>

[⛓️ [mariadb.com] "_Not null constraints_"](https://mariadb.com/docs/server/architecture/server-constraints/not-null-constraints)

Define whether a value can be `NULL` or not (by default `NULL`).
```SQL
CREATE TABLE {{table_name}}
(
    {{column_a}} {{datatype}} NOT NULL,
    {{column_b}} {{datatype}} -- By default NULL
);
```

## <div id="primary-key">6. Primary key</div>

[⛓️ [mariadb.com] "_Primary key constraints_"](https://mariadb.com/docs/server/architecture/server-constraints/primary-key-constraints)

Is like combine `NOT NULL`, `UNIQUE` and `INDEX`.
```SQL
CREATE TABLE {{table_name}}
(
    ...
    CONSTRAINT {{constraint_name}}
    PRIMARY KEY ({{column_a}})
)
```

## <div id="unique">7. Unique</div>

[⛓️ [mariadb.com] "_Create table - Unique_"](https://mariadb.com/docs/server/server-usage/tables/create-table#unique)

Force unique values for one or more columns.
```SQL
CREATE TABLE {{table_name}}
(
    ...
    CONSTRAINT {{constraint_name}}
    UNIQUE ({{column_a}}, {{column_b}}, ...)
);
```