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
COALESCE(value, default_value)
```

The second argument is the default value (by default `NULL`).

## If null

Replace `NULL` values with another.

**MariaDB & PostgreSQL**
```SQL
IFNULL(value, 0)
```

**SQL Server**
```SQL
ISNULL(value, default_value)
```