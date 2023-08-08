# Enable Logging

In the `postgresql.conf` file edit the following:

```shell
log_statement = 'all'
logging_collector = on
log_destination = 'csvlog'
log_directory = '/var/log/postgresql'
```

---

#### Refs

- Docs: https://www.postgresql.org/docs/current/runtime-config-logging.html
