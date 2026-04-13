[Home](../../readme.md) / MariaDB / Triggers

# Triggers

[⛓️ [mariadb.com] "_Triggers_"](https://mariadb.com/docs/server/server-usage/triggers-events/triggers)

Define a piece of code that runs automatically when a specific event occurs in a database.

They allow you to:
- Log data in a dedicated table
- Validate data before insertion (like `CHECK`)
- Synchronize tables

## Summary

1. [Create](#create)
2. [Drop](#drop)

## <div id="create">1. Create</div>

- `{{event_time}}` — Can be `BEFORE` or `AFTER`
- `{{event_type}}` — Can be `INSERT`, `UPDATE` or `DELETE`

```SQL
CREATE TRIGGER {{trigger_name}} 
{{event_time}} {{event_type}} ON {{table_a}}
FOR EACH ROW BEGIN 	
    UPDATE {{table_b}}
    SET {{column_a}} = {{column_b}} - NEW.{{column_c}} 	
    WHERE {{id}} = NEW.{{table_b_id}};
END;
```

## <div id="drop">2. Create</div>

```SQL
DROP TRIGGER {{trigger_name}};
```