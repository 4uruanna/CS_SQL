[Home](../../readme.md) / The basics / [Datas](../Datas.md) / Clone

# Clone

If you use the same names and the same order in both tables, you can also use a subquery to achieve this :
```SQL
INSERT INTO target_table
SELECT * FROM source_table
WHERE {{CONDITION}};
```

Otherwiser, you can use it like this

```SQL
INSERT INTO target_table (column_a, column_b, column_c, ...)
SELECT column_source_a, column_source_b, column_source_c, ...
FROM source_table
WHERE {{CONDITION}};
```