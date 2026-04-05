[Home](../../../readme.md) / Resources / [Operators](../Operators.md) / Text research

# Text research

```SQL
WHERE column_a LIKE {{PATTERN}}; 
```

| Wildcards | Description |
|-:|:-|
| `%` | Represents zero or multiple charaters |
| `_` | Represents a single character |

## Examples

All value beginning with 'a', 'b' or 'c':
```SQL
WHERE column_a LIKE '[a-c]%';
```