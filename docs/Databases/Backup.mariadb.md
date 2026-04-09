[Home](../readme.md) / The basics / [Databases](../Databases.md) / [Backup](./Backup.md) / MariaDB

[mariadb.com — "Backup and Restore Overview"](https://mariadb.com/docs/server/server-usage/backup-and-restore/backup-and-restore-overview)

# Backup — MariaDB

**The following commands are not SQL commands, but BASH commands that use tools built into the database.**

## Export

```BASH
mariadb-dump {{database_name}} > {{backup_file_name}}.sql
```

- Replace `{{database_name}}` with the name of the target database.
- Replace `{{backup_file_name}}` with the name of your choice.

## Restore

```BASH
mariadb {{database_name}} < {{backup_file_name}}.sql
```

- Replace `{{database_name}}` with the name of the target database.
- Replace `{{backup_file_name}}` with the name of your choice.