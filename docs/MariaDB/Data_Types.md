[Home](../../readme.md) / MariaDB / Data Types

# Data Types

[⛓️ [mariadb.com] "_Data Types_"](https://mariadb.com/docs/server/reference/data-types)

## Summary

1. [Numeric](#numeric)
    1. [Integer](#numeric-integer)
    2. [Decimal](#numeric-decimal)
2. [Text](#text)
3. [Date & Time](#date-and-type)
4. [Specific](#specific)

## <div id="numeric">1. Numeric</div>

You can combine any numeric type them with `UNSIGNED`.
```SQL
column_a SMALLINT UNSIGNED
```

### <div id="numeric-integer">1.1. Integer</div>

| Bytes | MariaDB | Max Range |
|-:|:-:|:-|
| 1 | `TINYINT` | 255 |
| 2 | `SMALLINT` | 65 535 |
| 3 | `MEDIUMINT` | 16 777 215 |
| 4 | `INT`, `INTEGER` | 4 294 967 295 |
| 8 | `BIGINT` | 18 446 744 073 709 551 615 |

### <div id="numeric-decimal">1.2. Decimal</div>

| Bytes | MariaDB |
|-:|:-:|
| 4 | `FLOAT` |
| 8 | `DOUBLE` |

## <div id="text">2. Text</div>

| — | Bytes |
|:-:|:-|
| `CHAR`, `TINYTEXT` | 255 |
| `TEXT` | 65,535 |
| `MEDIUMTEXT` | 16MB |
| `LONGTEXT` | 4GB |

## <div id="date-and-time">3. Date & Time</div>

| — |
|:-:|
| `DATE` |
| `TIME` |
| `DATETIME` |
| `TIMESTAMP` |
| `YEAR` |

### Format

| Type | Format |
|-:|:-|
| DATE | YYYY-MM-DD |
| DATETIME | YYYY-MM-DD HH:MI:SS |
| TIMESTAMP | YYYY-MM-DD HH:MI:SS |
| TIME | HH:MI:SS |
| YEAR |format YYYY or YY |

## <div id="specific">4. Specific</div>

| — |
|:-:|
| `UUID` |
| `JSON` |
| `BLOB` |