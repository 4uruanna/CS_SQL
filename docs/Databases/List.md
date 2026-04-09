[Home](../readme.md) / The basics / [Databases](../Databases.md) / List

# List

_List all databases._

| Engine | Code |
|-:|:-|
| PostgreSQL | `SELECT datname FROM pg_database;`|
| MariaDB | `SELECT schema_name FROM information_schema.schemata;`|
| SQL Server | `SELECT schema_name FROM information_schema.schemata;`|

> Note: Don't worry if you see databases that don't belong to you. Some databases are created by your engine to ensure it runs properly.
