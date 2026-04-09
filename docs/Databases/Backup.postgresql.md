

[Home](../readme.md) / The basics / [Databases](../Databases.md) / [Backup](./Backup.md) / PostgreSQL

[postgresql.org — "pg_dump"](https://www.postgresql.org/docs/current/app-pgdump.html)  
[postgresql.org — "pg_restore"](https://www.postgresql.org/docs/current/app-pgrestore.html)

# Backup — PostgreSQL

**The following commands are not SQL commands, but BASH commands that use tools built into the database.**

## Export

```BASH
pg_dump --format=plain {{database_name}} > {{backup_file_name}}.sql
```

- Replace `{{database_name}}` with the name of the target database.
- Replace `{{backup_file_name}}` with the name of your choice.

## Restore

```BASH
pg_restore --format=plain -d {{database_name}} {{backup_file_name}}.sql
```

- Replace `{{database_name}}` with the name of the target database.
- Replace `{{backup_file_name}}` with the name of your choice.