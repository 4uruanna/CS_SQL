[Home](../readme.md) / The basics / Views

# Views

Views are virtual tables based on the result set of an SQL statement.

A view always displays data in real time and does not copy it (only the view definition is stored).

## Create
```SQL
CREATE VIEW view_name
AS SELECT column_a, column_b, ...
FROM table_name
WHERE {{CONDITION}};
```

## Delete
```SQL
DROP VIEW view_name;
```

## Select
```SQL
SELECT * FROM view_name;
```

## Update
```SQL
CREATE OR REPLACE VIEW view_name
AS SELECT column_a, column_b, ...
FROM table_name
WHERE condition;
```


[← ](./.md) ◎ [ →](./.md)