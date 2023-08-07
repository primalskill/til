# Find the Owner of a Table

```sql
SELECT * FROM pg_tables WHERE tablename ILIKE '%my_table_name%';
```

---

#### Refs

- Docs: https://www.postgresql.org/docs/current/view-pg-tables.html
