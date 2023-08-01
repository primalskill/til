# Use Database NULL Value Types

If a database table column can contain NULL values, then use the NULL value types from the `database/sql` package. There are NullXXX types for the most common data types like bool, time, string, etc.
  
  
```golang

import "database/sql"

...

var s NullString
err := db.QueryRow("SELECT name FROM foo WHERE id=?", id).Scan(&s)

...

if s.Valid {
   // use s.String
} else {
   // NULL value
}
```

---

**Refs**

- https://pkg.go.dev/database/sql#NullString
