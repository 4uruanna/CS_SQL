[Home](../../../readme.md) / Resources / [Operators](../Operators.md) / Comparison

# Comparison


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

## Examples

```SQL
WHERE column_a = 1;

WHERE NOT column_a = 1;

WHERE column_a IS NOT NULL;

WHERE column_a NOT BETWEEN 100 and 200;

WHERE column_a > ALL (SELECT column_b from table_b);

WHERE column_a = ANY (SELECT column_b from table_b);

SELECT * FROM table_a
WHERE EXISTS (
    SELECT column_b FROM table_b
    WHERE table_b.id = table_a.id
);
```