# Secure Copying Files

Use the `scp` command that uses `ssh` underneath for copying to/from servers.

From local machine to server:

```shell
scp myfile.txt server.host:./path/on/server/myfile.txt
```

From server to local machine:

```shell
scp server.host:./path/on/server/myfile.txt .
```
