[Home](../../readme.md) / MariaDB / Database

# Databases

Now that you have chosen and installed your databases engine.

The first thing you need to do is to understand the basics of database manipulation.

## Summary

1. [Backup](#backup)
    1. [Export](#backup-export)
    2. [Restore](#backup-restore)
2. [Clone](#clone)
3. [Create](#create)
4. [Drop](#drop)
5. [List](#list)
6. [Rename](#rename)

## <div id="backup">1. Backup</div>

[⛓️ [mariadb.com] "_Backup and Restore Overview_"](https://mariadb.com/docs/server/server-usage/backup-and-restore/backup-and-restore-overview)

**The following commands are not SQL commands, but BASH commands that use tools built into the database.**

### <div id="backup-export">1.1. Export</div>

```BASH
mariadb-dump {{database_name}} > {{backup_file_name}}.sql
```

### <div id="backup-restore">1.2. Restore</div>

```BASH
mariadb {{database_name}} < {{backup_file_name}}.sql
```

## <div id="clone">2. Clone</div>

There is no built-in solution in MariaDB to clone database.

The easyest way is to export (1.1) and restore (1.2) it with different name.

## <div id="create">3. Create</div>

[⛓️ [mariadb.com] "_Create database_"](https://mariadb.com/docs/server/reference/sql-statements/data-definition/create/create-database)

```SQL
CREATE DATABASE {{database_name}};
```

## <div id="drop">4. Drop</div>

[⛓️ [mariadb.com] "_Drop database_"](https://mariadb.com/docs/server/reference/sql-statements/data-definition/drop/drop-database)

```SQL
DROP DATABASE {{database_name}};
```

## <div id="list">5. List</div>

[⛓️ [mariadb.com] "_Information Schema_"](https://mariadb.com/docs/server/reference/system-tables/information-schema)

```SQL
SELECT SCHEMA_NAME FROM information_schema.schemata;
```

> `information_schema` is a standard-compliant database that exposes metadata about the server.

> Don't worry if you see databases that don't belong to you. Some databases are created by your server to ensure it runs properly.

## <div id="rename">6. Rename</div>


[⛓️ [mariadb.com] "_Renaming databases_"](https://mariadb.com/docs/server/reference/sql-statements/data-definition/renaming-databases)


```SQL
CREATE DATABASE {{new_database_name}};

-- Do this for every table in database {{old}}
RENAME TABLE {{old_database_name}}.{{table_name}}
TO {{new_database_name}}.{{table_name}};

-- When no table is left in database {{old}}, optionally drop it
DROP DATABASE {{old_database_name}};
```
