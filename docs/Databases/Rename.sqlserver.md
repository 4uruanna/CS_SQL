[Home](../readme.md) / The basics / [Databases](../Databases.md) / [Rename](./Rename.md) / SQL Server

[learn.microsoft.com — "Rename a database"](https://learn.microsoft.com/en-us/sql/relational-databases/databases/rename-a-database)

# Rename / SQL Server

```SQL
-- Connect to `master` database --
USE master;
GO

-- All incomplete transactions to be rolled back and any other connections to be immediately disconnected. --
ALTER DATABASE {{old}} SET SINGLE_USER WITH ROLLBACK IMMEDIATE; 
GO

ALTER DATABASE {{old}} MODIFY NAME = {{new}};
GO

ALTER DATABASE {{new}} SET MULTI_USER;
GO
```

- Replace `{{old}}` with the name of the target database.
- Replace `{{new}}` with the new name of your choice.
