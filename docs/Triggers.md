[Home](../readme.md) / The basics / Triggers

# Triggers

Define a piece of code that runs automatically when a specific event occurs in a database.

They allow you to:
- Log data in a dedicated table
- Validate data before insertion (like `CHECK`)
- Synchronize tables

- `{{EVENT_TIME}}` — Can be `BEFORE` or `AFTER`
- `{{EVENT_TYPE}}` — Can be `INSERT`, `UPDATE` or `DELETE`

**MariaSQL**  
`NEW`
```SQL
CREATE TRIGGER trigger_name 
{{EVENT_TIME}} {{EVENT_TYPE}} ON table_a
FOR EACH ROW BEGIN 	
    UPDATE table_b
    SET column_a = column_b - NEW.column_c 	
    WHERE id = NEW.table_b_id;
END;
```

**PostgreSQL**  
`NEW`  
Require a dedicated function to call.
```SQL
CREATE OR REPLACE FUNCTION function_name() 
RETURNS TRIGGER AS $$ 
BEGIN 
    UPDATE table_b
    SET column_a = column_b - NEW.column_c 	
    WHERE id = NEW.table_b_id;
END; $$ 

LANGUAGE plpgsql; 
CREATE TRIGGER trigger_name 
{{EVENT_TIME}} {{EVENT_TYPE}} ON table_a 
FOR EACH ROW 
EXECUTE FUNCTION function_name();
```

**SQL Server**  
`SELECT column_c FROM inserted`

```SQL
CREATE TRIGGER trigger_name
ON table_a
{{EVENT_TIME}} {{EVENT_TYPE}}
AS BEGIN 
    UPDATE table_b
    SET column_a = column_b - (SELECT column_c FROM inserted)
    WHERE id = NEW.table_b_id;
END;
```

[← Stored Procedures](./Stored_Procedures.md) ◎ [Triggers →](./Triggers.md)