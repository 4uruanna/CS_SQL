[Home](../readme.md) / The basics / [Databases](../Databases.md) / Clone

# Clone

**MariaDB**

There is no easy solution. You need to [export](./Backup.md) and restore it using using another name.

**PostgreSQL** 
```SQL
CREATE DATABASE db_clone WITH TEMPLATE db_source;
```

**SQL Server**

There is no easy solution. You need to [export](./Backup.md) and restore it using using another name.
