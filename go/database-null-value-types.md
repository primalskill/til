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


### Update (2025)

Just to clarify, `database/sql` `NullXXX` functions are essentially pointers. You can simplify the above code like so:

```golang

var s *string

err := db.QueryRow("SELECT name FROM foo WHERE id=?", id).Scan(&s)

...

if s != nil {
  // use s value
} else {
  // NULL value
}

```


---

**Refs**

- https://pkg.go.dev/database/sql#NullString
