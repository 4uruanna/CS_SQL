[Home](../../readme.md) / MariaDB / Optimizations

# Optimizations

## Summary

1. [Analyze](#analyze)
2. [Best practices](#best-practices)
3. [Index](#index)

## <div id="analyze">1. Analyze</div>

[⛓️ [mariadb.com] "_Explain_"](https://mariadb.com/docs/server/reference/sql-statements/administrative-sql-statements/analyze-and-explain-statements/explain)

`EXPLAIN` generates an estimate of the execution time.
With `ANALYZE` it executes the query in real time and records the execution time.

```SQL
EXPLAIN ANALYSE
SELECT column_a, column_b, ...
FROM table_name
WHERE {{CONDITION}}
```

- In the output, "Rows" indicates the number of lines that have been checked. You should be able to optimize any sub-query of the `ALL` "Type".
- In the output if "Extra" indicates "Using temporary" or "Using filesort" that means : the database must create a temporary table on disk or in memory to handle your data (often because of an `ORDER BY` clause without an index) and this is very resource-intensive.

## <div id="best-practices">2. Best practices</div>

- Limit numbers of columns returned (avoid `*`).
- Limit result using `LIMIT` and `OFFSET`.
- Use only indexed foreign keys.
- If possible, reduce the size of the tables using a `WHERE` clause before joins.
- Avoid using functions in the `WHERE` clause as much as possible.
- If possible, use `JOIN` instead of subquery operator (such as `IN`, `EXISTS`, etc.)

## <div id="index">3. Index</div>

[⛓️ [mariadb.com] "_Indexes guide_"](https://mariadb.com/docs/server/server-usage/tables/mariadb-indexes-guide-1)

To improve performance, you can index the filter columns (any columns used in a `WHERE`, `JOIN`, `ORDER BY`, or `GROUP BY` clause can be indexed.

If you frequently filter by last A AND first B, a composite index on `(A, B)` is more efficient than two separate indexes.

⚠︎ WARNING ⚠︎ Each index slows down `INSERT`, `UPDATE`, and `DELETE` operations because the database must update the index with every change.

```SQL
CREATE INDEX index_name
ON table_name (column_a, column_b, ...);
```

See more into [Tables / Update](./Tables/Update.md).