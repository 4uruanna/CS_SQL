[Home](../../readme.md) / Resources / Constraints

# Constraints

Constraints are rules for data in a table. They can be declared in [`CREATE TABLE`](../Tables/Create.md) and [`ALTER TABLE`](../Tables/Update.md).


## AUTO_INCREMENT

Automatically increments a value without having to manage it manually. Commonly used with `PRIMARY KEY`.
```SQL
column_a INT AUTO_INCREMENT PRIMARY KEY;
```

## CHECK

Restricts the values accepted by one or multiple columns.
```SQL
CREATE TABLE table_name
(
    column_a INT NOT NULL,
    column_b INT NOT NULL,
    CONSTRAINT constraint_name CHECK (
        column_a > value_a
        AND column_b <> value_b
    )
);
```

## DEFAULT

Define default value.
```SQL
CREATE TABLE table_name
(
    column_a INT DEFAULT 666;
);
```

## FOREIGN KEY

Establishes a relationship with another table.
```SQL
CONSTRAINT constraint_name
FOREIGN KEY (column_a)
REFERENCES table_b(column_b)
```

## NULL / NOT NULL

Define whether a value can be `NULL` or not (by default `NULL`).
```SQL
CREATE TABLE table_name
(
    column_a INT NOT NULL,
    column_b INT NULL,
    column_c INT -- By default NULL
);
```

## PRIMARY KEY

Is like combine `NOT NULL`, `UNIQUE` and `INDEX`.
```SQL
CONSTRAINT constraint_name PRIMARY KEY (column_a)
```

## UNIQUE

Force unique values for one or more columns.
```SQL
CREATE TABLE table_name
(
    column_a INT NOT NULL,
    column_b TEXT NOT NULL,
    CONSTRAINT constraint_name UNIQUE (column_a, column_b)
);
```