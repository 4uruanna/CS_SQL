[Home](../../readme.md) / The basics / [Tables](../Tables.md) / List

# List


| Engine | Code |
|-:|:-|
| PostgreSQL | `SELECT table_schema, table_name FROM information_schema.tables;` |
| MariaDB | `SELECT table_name FROM information_schema.tables WHERE table_schema = 'database_name';` |
| SQL Server | `SELECT name FROM sys.tables;` |
