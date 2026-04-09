[Home](../readme.md) / The basics / [Databases](../Databases.md) / [Rename](./Rename.md) / MariaDB

[mariadb.com — "Renaming databases"](https://mariadb.com/docs/server/reference/sql-statements/data-definition/renaming-databases)

# Rename / MariaDB

```SQL
CREATE DATABASE {{new}};
-- Do this for every table in database {{old}}
RENAME TABLE {{old}}.t TO {{new}}.t;
-- When no table is left in database {{old}}, optionally drop it
DROP DATABASE {{old}};
```

- Replace `{{old}}` with the name of the target database.
- Replace `{{new}}` with the new name of your choice.