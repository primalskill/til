# Journalctl Show One Unit

Viewing only one `systemd` unit in `journalctl`; and add `--reverse` so the most recent logs are shown first.

```shell
journalctl --unit=my_unit --reverse
```
