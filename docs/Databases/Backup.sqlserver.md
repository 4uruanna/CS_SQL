

[Home](../readme.md) / The basics / [Databases](../Databases.md) / [Backup](./Backup.md) / SQL Server

[learn.microsoft.com — "Create a full database backup"](https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/create-a-full-database-backup-sql-server?view=sql-server-ver17)

# Backup — SQL Server

## Export

```BASH
BACKUP DATABASE {{database_name}}
TO DISK = '{{backup_filepath}}/{{backup_file_name}}.bak';
```

And if you want to back up only the changes made since your last full backup:

```SQL
BACKUP DATABASE {{database_name}}
TO DISK = '{{backup_filepath}}/{{backup_file_name}}.bak';
WITH DIFFERENTIAL;
```

- Replace `{{database_name}}` with the name of the target database.
- Replace `{{backup_file_name}}` with the name of your choice.

## Restore

```BASH
USE master;
GO

RESTORE DATABASE {{database_name}}
FROM DISK = '{{backup_filepath}}/{{backup_file_name}}.bak'
RECOVERY;
```

- Replace `{{database_name}}` with the name of the target database.
- Replace `{{backup_file_name}}` with the name of your choice.