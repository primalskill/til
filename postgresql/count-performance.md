# Count Performance

The slow performance of `COUNT(*)` is a thing of the past.

There's really no difference between various `COUNT` methods. The query planner is smart enough to know what you want to do.

```sql
SELECT COUNT(*) FROM my_table;

SELECT COUNT(id) FROM my_table;

SELECT COUNT(1) FROM my_table;
```

The above queries will result in the same record-counting strategy and will have the same cost.
