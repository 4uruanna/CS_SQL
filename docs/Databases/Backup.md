[Home](../readme.md) / The basics / [Databases](../Databases.md) / Backup

# Backup

## EXPORT

**MariaDB**  
No SQL exists to do it so you need to use your terminal.
```BASH
mariadb-dump -u username -p db_name > filename.sql
```

**PostgreSQL**  
No SQL exists to do it so you need to use your terminal.
```BASH
pg_dump --username=username --format=plain db_name > filename.sql
```

```BASH
pg_dump --username=username db_name > filename.dump
```

**SQL Server**
```SQL
BACKUP DATABASE nom_base 
TO DISK = 'C:\backups\nom_base.bak';
```

And if you want to back up only the changes made since your last full backup:

```SQL
BACKUP DATABASE db_name
TO DISK = 'filepath/filename.bak';
WITH DIFFERENTIAL;
```

## RESTORE

**MariaDB**  
No SQL exists to do it so you need to use your terminal.
```BASH
mariadb -u username -p db_name < filename.sql
```

**PostgreSQL**  
No SQL exists to do it so you need to use your terminal.
```BASH
psql --username=username -d db_name -f filename.sql
```
```BASH
pg_restore --username=username -d nom_base -v "filename.dump"
```

**SQL Server**
```SQL
USE master;
GO
RESTORE DATABASE db_name
FROM DISK = 'filepath/filename.bak'
RECOVERY;
```


