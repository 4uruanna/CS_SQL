[Home](../readme.md) / The basics / [Databases](../Databases.md) / Clone

[postgresql.org — "Create database"](https://www.postgresql.org/docs/current/sql-createdatabase.html)

# Clone

_Duplicate database_

| Engine | Code |
|-:|:-|
| PostgreSQL | `CREATE DATABASE {{clone_name}} WITH TEMPLATE {{source_name}};`|
| MariaDB | There is no easy solution. You can [export and restore](./Backup.mariadb.md) it with different name. |
| SQL Server | There is no easy solution. You can [export and restore](./Backup.sqlserver.md) it with different name. |

- Replace `{{source_name}}` with the name of the target database.
- Replace `{{clone_name}}` with the name of the clone database.
