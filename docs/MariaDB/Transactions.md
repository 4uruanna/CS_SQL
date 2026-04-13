[Home](../../readme.md) / MariaDB / Transactions

# Transactions

## Summary

1. [Basics](#basics)
2. [Savepoints](#savepoints)

## <div id="basics">1. Basics</div>

[⛓️ [mariadb.com] "_Transactions_"](https://mariadb.com/docs/server/reference/sql-statements/transactions)

A transaction allows you to group one or more statements. It ensures that all operations are completed before being committed, thereby preserving data integrity.

- `START TRANSACTION` is used to begin a transaction.
- `COMMIT` is used to apply changes and end transaction.
- `ROLLBACK` is used to discard changes and end transaction.


```SQL
START TRANSACTION;

-- Statement 1
UPDATE table_a
SET column_a = column_a - 10
WHERE column_b = value_b;


-- Statement 1
UPDATE table_b
SET column_c = column_c + 10
WHERE column_d = value_d;

COMMIT;
```

If any update fails, `ROLLBACK` cancels all changes to maintain consistency.

```SQL
ROLLBACK;
```

## <div id="savepoints">2. Savepoints</div>

[⛓️ [mariadb.com] "_Savepoint_"](https://mariadb.com/docs/server/reference/sql-statements/transactions/savepoint)

Allows you to create a reference (like GOTO) point within a transaction using `SAVEPOINT` keyword.  
Using `RELEASE SAVEPOINT` to release the most recent savepoint makes the previous one accessible again to the `ROLLBACK TO SAVEPOINT` and `RELEASE SAVEPOINT` commands.

```SQL
START TRANSACTION;
    INSERT INTO table_a VALUES (1);
    SAVEPOINT transaction_name; -- 1ft
    INSERT INTO table_a VALUES (2);
    SAVEPOINT transaction_name; -- 2nd
    INSERT INTO table_a VALUES (3);

    -- rollback (2nd savepoint)
    ROLLBACK TO SAVEPOINT transaction_name;
    SELECT * FROM table_a; -- display: 1, 2

    -- free 2nd savepoint
    RELEASE SAVEPOINT transaction_name;

    -- rollback 1ft savepoint
    ROLLBACK TO SAVEPOINT transaction_name;
    SELECT * FROM table_a; -- display: 1
    RELEASE SAVEPOINT transaction_name;
    
    SAVEPOINT transaction_name; -- new 1ft
    INSERT INTO table_b (column_a) VALUES (1);
    INSERT INTO table_b (column_a) VALUES ('Error'); -- Trigger an error
    ROLLBACK TO SAVEPOINT transaction_name; -- Cancel insert 1
    INSERT INTO table_a (column_a) VALUES (2); -- Insert 2 instead
    RELEASE SAVEPOINT transaction_name;
COMMIT;
```