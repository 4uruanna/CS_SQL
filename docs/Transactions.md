[Home](../readme.md) / The basics / Transactions

# Transactions

A transaction allows you to group one or more statements. It ensures that all operations are completed before being committed, thereby preserving data integrity.

```SQL
BEGIN TRANSACTION transaction_name ;

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

[← Query customization](./Query_customization.md) ◎ [Views →](./Views.md)