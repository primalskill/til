# Backup & Restore

## Backup

Use `pg_dump` and `pg_dumpall` if possible in CLI to back up a database.

```shell
pg_dump --format=plain --file=output.sql my_database
```

_Note that pg_restore can't restore plain formats, in this case use --format=custom_

If admin privileges are needed:

```shell
sudo -u postgres pg_dump --format=plain --file=output.sql my_database
```

Dumping globals and/or clusters:

```shell
pg_dumpall --globals-only
```

_Always test the backup file by restoring it to a separate database._

## Restore

Use `pg_restore` to restore a backup file. Note pg_restore can only restore custom format backup files, not plain ones.

```shell
pg_restore --format=custom --dbname=my_database output.sql
```

If admin privileges are needed:

```shell
sudo -u postgres pg_restore --format=custom --dbname=my_database output.sql
```

If importing into a database owned by another user, don't emit owner statements:

```shell
pg_restore --format=custom --dbname=my_database --no-owner output.sql
```

Use `psql` to restore plain SQL backup files:

``` shell
psql my_database < output.sql
```

---

#### Refs

- https://www.postgresql.org/docs/current/app-pgdump.html
- https://www.postgresql.org/docs/current/app-pgrestore.html
- https://www.postgresql.org/docs/current/app-psql.html
