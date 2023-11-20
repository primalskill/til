# Escaping Single Quotes

According to the SQL standard escaping single quotes should be done with another single quote.

```sql
INSERT INTO mytable (name) VALUES ('Shaquille O''Neal')
```

Note: See the two single quotes in `O''Neal`

-----

### Refs

- [PostgreSQL Docs - String Constants](https://www.postgresql.org/docs/16/sql-syntax-lexical.html#SQL-SYNTAX-STRINGS)
