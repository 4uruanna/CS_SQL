[Home](../../../readme.md) / Resources / [Operators](../Operators.md) / Logical

# Logical

| Operator | Description |
|-:|:-|
| `AND` | Combine conditions |
| `OR` | Add conditions |
| `IN (...)` | In a list |
| `BETWEEN ... AND ...` | If in range |

## Examples

**In**
```SQL
WHERE column_a IN ('Alice', 'Bob');

WHERE column_a IN (SELECT column_b FROM table_b);
```

**Between**
```SQL
WHERE column_a BETWEEN 1 AND 2;

WHERE BETWEEN 'Alice' AND 'Bob'
ORDER BY column_a;

WHERE column_a BETWEEN '2009-09-09' AND '2012-12-12';
```