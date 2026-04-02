[Home](../readme.md) / The basics / [Databases](../Databases.md) / Rename

# Rename

**MariaDB**

There is no easy solution. You can follow [this official article](https://mariadb.com/docs/server/reference/sql-statements/data-definition/renaming-databases).

**PostgreSQL** 
```SQL
ALTER DATABASE old_name RENAME TO new_name;
```

**SQL Server**
```SQL
ALTER DATABASE old_name MODIFY NAME = new_name;
```
