# Upgrade PostgreSQL

Upgrading minor or major versions is done using `pg_upgrade`.

### 1. Update and install the new PostgreSQL packages

```shell
apt-get update
apt-get install postgresql-16 postgresql-server-dev-16
```

### 2. Copy over the old configs from the old version

_Notes:_

- Assuming the old PostgreSQL version is 15.
- There could be compatibility problems between the config files of major versions, like in v16 some conf variables are dropped, so make sure it's compatible.

```shell
cp /etc/postgresql/15/main/postgresql.conf /etc/postgresql/16/main/postgresql.conf
cp /etc/postgresql/15/main/pg_hba.conf /etc/postgresql/16/main/pg_hba.conf
```

### 3. Stop the old cluster

```shell
system postgresql stop
```

### 4. Log in as the postgres user

_Notes:_

- Don't switch to another folder once logged in as the `postgres` user.

```shell
sudo su - postgres
```

### 5. Upgrade

```shell
/usr/lib/postgresql/16/bin/pg_upgrade \
  --old-datadir=/var/lib/postgresql/15/main \
  --new-datadir=/var/lib/postgresql/16/main \
  --old-bindir=/usr/lib/postgresql/15/bin \
  --new-bindir=/usr/lib/postgresql/16/bin \
  --old-options '-c config_file=/etc/postgresql/15/main/postgresql.conf' \
  --new-options '-c config_file=/etc/postgresql/16/main/postgresql.conf' \
  --check
```

If everything OK, upgrade the version. Without `--check`

```shell
/usr/lib/postgresql/16/bin/pg_upgrade \
  --old-datadir=/var/lib/postgresql/15/main \
  --new-datadir=/var/lib/postgresql/16/main \
  --old-bindir=/usr/lib/postgresql/15/bin \
  --new-bindir=/usr/lib/postgresql/16/bin \
  --old-options '-c config_file=/etc/postgresql/15/main/postgresql.conf' \
  --new-options '-c config_file=/etc/postgresql/16/main/postgresql.conf'
```

### 6. Start the new cluster

_Notes:_

- Exit as the `postgres` user and return to `root`.

```shell
exit
service postgresql start
```

### 7. Vacuum the DBs

_Notes:_

- Log back in with the `postgres` user.

```shell
sudo su - postgres
/usr/lib/postgresql/16/bin/vacuumdb --all --analyze-in-stages
```

### 7. Remove old cluster packages

_Notes:_

- Exit as the `postgres` user and return to `root`.
- **DO NOT** remove the `*-common` packages.

```shell
exit
apt list --installed | grep PostgreSQL

apt-get remove postgresql-15 postgresql-server-dev-15 postgresql-client-15

rm -rf /etc/postgresql/15/
```

### 8. Remove the old cluster data directory

_Notes:_

- Log back in with the `postgres` user.

```shell
sudo su - postgres
./delete_old_cluster.sh
```


---

#### Refs

- https://www.postgresql.org/docs/current/pgupgrade.html
