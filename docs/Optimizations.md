[Home](../readme.md) / The basics / Optimizations

# Optimizations

## Analyze

`EXPLAIN` generates an estimate of the execution time.
With `ANALYZE` it executes the query in real time and records the execution time.

```SQL
EXPLAIN ANALYSE
SELECT column_a, column_b, ...
FROM table_name
WHERE {{CONDITION}}
```

- In the output, "Rows" indicates the number of lines that have been checked. You should be able to optimize any sub-query of the `ALL` "Type".
- In the output if "Extra" indicates "Using temporary" or "Using filesort" that means : the database must create a temporary table on disk or in memory to handle your data (often because of an [`ORDER BY`](./Query_customization.md) clause without an index) and this is very resource-intensive.

## Best practices

- Limit numbers of columns returned (avoid `*`).
- Limit result using [`LIMIT`](./Query_customization.md) and [`OFFSET`](./Query_customization.md).
- Use only indexed foreign keys.
- If possible, reduce the size of the tables using a `WHERE` clause before joins.
- Avoid using functions in the `WHERE` clause as much as possible.

## Index

To improve performance, you can index the filter columns (any columns used in a `WHERE`, [`JOIN`](./Joins.md), [`ORDER BY`](./Query_customization.md), or [`GROUP BY`](./Query_customization.md) clause can be indexed.

If you frequently filter by last A AND first B, a composite index on `(A, B)` is more efficient than two separate indexes.

⚠︎ WARNING ⚠︎ Each index slows down [`INSERT`](./Datas/Create.md), [`UPDATE`](./Datas/Update.md), and [`DELETE`](./Datas/Delete.md) operations because the database must update the index with every change.

```SQL
CREATE INDEX index_name
ON table_name (column_a, column_b, ...);
```

See more into [Tables / Update](./Tables/Update.md).

[← ](./.md) ◎ [ →](./.md)