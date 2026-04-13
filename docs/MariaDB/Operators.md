[Home](../../readme.md) / MariaDB / Operators

# Operators

[⛓️ [mariadb.com] "_Function and operator reference_"](https://mariadb.com/docs/server/reference/sql-functions/function-and-operator-reference)

## Summary

1. [Arithmetic](#arithmetic)
2. [Comparison](#comparison)
3. [Logical](#logical)
4. [Text research](#text-research)

## <div id="arithmetic">1. Arithmetic</div>

| Operator | Description |
|-:|:-|
| `+` | Add |
| `-` | Substract |
| `*` | Multiply |
| `/` | Divide |
| `%` | Modulo (Remainder of the division) |
| `&` | Bitwise AND |
| `\|` | Bitwise OR |
| `^` | Bitwise XOR |
| `~` | Bitwise NOT |

## <div id="comparison">2. Comparison</div>

| Operator | Description |
|-:|:-|
| `=` | Equal |
| `>` | Greater |
| `<` | Lower |
| `>=` | Greater or Equal |
| `<=` | Lower or Equal |
| `<>`, `!=`, `NOT` | Different or reverse |
| `IS NULL` | Is null |
| `ALL` | Compares a value to a set of values from a subquery. This operator must be preceded by a standard comparison operator (`=`, `>`, `<>`...)  |
| `ANY` | Compares a value to a set of values from a subquery and is valid if one of them is correct. |
| `EXISTS` | If a value exists in a result-set of subquery |

**Examples**
```SQL
WHERE {{column_a}} = 1;

WHERE NOT {{column_a}} = 1;

WHERE {{column_a}} IS NOT NULL;

WHERE {{column_a}} NOT BETWEEN 100 and 200;

WHERE {{column_a}} > ALL (SELECT {{column_b}} from {{table_b}});

WHERE {{column_a}} = ANY (SELECT {{column_b}} from {{table_b}});

SELECT * FROM {{table_a}}
WHERE EXISTS (
    SELECT {{column_b}} FROM {{table_b}}
    WHERE {{table_b}}.id = {{table_a}}.id
);
```

## <div id="logical">3. Logical</div>

| Operator | Description |
|-:|:-|
| `AND` | Combine conditions |
| `OR` | Add conditions |
| `IN (...)` | In a list |
| `BETWEEN ... AND ...` | If in range |

**Example In**
```SQL
WHERE {{column_a}} IN ('Alice', 'Bob');

WHERE {{column_a}} IN (SELECT column_b FROM table_b);
```

**Example Between**
```SQL
WHERE {{column_a}} BETWEEN 1 AND 2;

WHERE BETWEEN 'Alice' AND 'Bob'
ORDER BY {{column_a}};

WHERE {{column_a}} BETWEEN '2009-09-09' AND '2012-12-12';
```

## <div id="text-research">4. Text research</div>

```SQL
WHERE {{column_a}} LIKE {{pattern}}; 
```

| Wildcards | Description |
|-:|:-|
| `%` | Represents zero or multiple charaters |
| `_` | Represents a single character |

```SQL
WHERE {{column_a}} LIKE '[a-c]%';
```
_All value beginning with 'a', 'b' or 'c'_
