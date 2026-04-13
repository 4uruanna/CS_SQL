[Home](../../readme.md) / The basics / [Tables](../Tables.md) / Clone

[postgresql.org — "Create table"](https://www.postgresql.org/docs/current/sql-createtable.html)  
[learn.microsoft.com — "SELECT - INTO clause"](https://learn.microsoft.com/en-us/sql/t-sql/queries/select-into-clause-transact-sql?view=sql-server-ver17)

# Clone

| Engine | Code |
|-:|:-|
| PostgreSQL | `CREATE TABLE {{clone_name}} (LIKE table_source INCLUDING ALL);`|
| MariaDB | `CREATE TABLE {{clone_name}} LIKE {{source_name}};`|
| SQL Server | `SELECT * INTO {{clone_name}} FROM {{source_name}} WHERE {{CONDITION}};`|

- Replace `{{source_name}}` with the name of the target table.
- Replace `{{clone_name}}` with the name of the clone table.

Cloned rules:
| Engine | Primary key | Foreign key | Index | Default | Check |
|-:|:-:|:-:|:-:|:-:|:-:|
| PostgreSQL | Yes | No | Yes | Yes | Yes |
| MariaDB | Yes | No | Yes | Yes | Yes |
| SQL Server | No | No | No | No | No |
