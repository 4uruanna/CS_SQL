[Home](../../../readme.md) / Resources / [Functions](../Functions.md) / Others

# Others

## Cast

**MariaDB**
```SQL
CAST(value as {{DATATYPE}})
```

**PostgreSQL**
```SQL
value::{{DATATYPE}}
```

**SQL Server**
```
CONVERT({{DATATYPE}}, value)
```

## Coalesce

Return the first non-`NULL` value.
```SQL
COALESCE(column_b, 0)
```

The second argument is the default value (by default `NULL`).

## If null

Replace `NULL` values with another.
```SQL
IFNULL(column_b, 0)
```