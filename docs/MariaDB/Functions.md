[Home](../../readme.md) / MariaDB / Functions

# Functions

[⛓️ [mariadb.com] "_Sql Functions_"](https://mariadb.com/docs/server/reference/sql-functions)

## Summary

1. [Aggregate](#aggregate)
2. [Math](#math)
3. [Others](#others)
4. [String](#string)

## <div id="aggregate">1. Aggregate</div>

### Average

```SQL
SELECT AVG(column_a) FROM table_name;
```

### Count

```SQL
SELECT COUNT(*) FROM table_name;
``` 

### Max

```SQL
SELECT MAX(column_a) FROM table_name;
```
### Min

```SQL
SELECT MIN(column_a) FROM table_name;
```

### Sum

```SQL
SELECT SUM(column_a) FROM table_name;
```

## <div id="math">2. Math</div>

### Absolute

```SQL
ABS(value)
```

### Ceil (Round up)

```SQL
CEIL(value)
```

### Floor (Round down)

```SQL
FLOOR(value)
```

### Pow

```SQL
POW(value, power)
```

### Round

```SQL
ROUND(value, d)
```

- `d` represents the desired number of decimal places (by default 0).

### Sign

Return the sign or `value` (`-1`, `0` or `1`).
```SQL
SIGN(value)
```

### Square

```SQL
SQRT(value)
```

## <div id="others">3. Others</div>

### Cast

```SQL
CAST(value as {{datatype}})
```

### Coalesce

Return the first non-`NULL` value.
```SQL
COALESCE(value, default_value)
```

The second argument is the default value (by default `NULL`).

### If null

Replace `NULL` values with another.

```SQL
IFNULL(value, 0)
```

## <div id="string">4. String</div>

### Concat

```SQL
CONCAT(column_a, ', ', column_b)
```

### Uppercase

```SQL
UPPER(value)
```

### Lowercase

```SQL
LOWER(value)
```

### Length

```SQL
LENGTH(value)
```

### Repeat
```SQL
REPEAT(value, count)
```

### Replace
```SQL
REPLACE(value, target_str, replace_by)
```

### Reverse
```SQL
REVERSE(value)
```

### Substring
```SQL
SUBSTRING(value, offset, length)
```

### Trim
```SQL
TRIM(value)
RTRIM(value) -- only right
LTRIM(value) -- only left
```