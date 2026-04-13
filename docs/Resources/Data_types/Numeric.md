[Home](../../../readme.md) / Resources / [Data Types](../Data_Types.md) / Numeric

# Numeric

You can combine any numeric type them with `UNSIGNED`:

```SQL
column_a SMALLINT UNSIGNED
```

## Integer

| Bytes | MariaDB | PostgreSQL | SQL Server | Max Range |
|-:|:-:|:-:|:-:|:-|
| 1 | `TINYINT` | `BOOLEAN` | `TINYINT` | 255 |
| 2 | `SMALLINT` | `SMALLINT` | `SMALLINT` |  65 535 |
| 3 | `MEDIUMINT` | N/A | N/A | 16 777 215 |
| 4 | `INT`, `INTEGER` | `INTEGER` | `INT` | 4 294 967 295 |
| 8 | `BIGINT` | `BIGINT` | `BIGINT` | 18 446 744 073 709 551 615 |

## Decimal

| Bytes | MariaDB | PostgreSQL | SQL Server |
|-:|:-:|:-:|:-:|
| 4 | `FLOAT` | `REAL` | `REAL` |
| 8 | `DOUBLE` | `FLOAT` | `FLOAT` |
