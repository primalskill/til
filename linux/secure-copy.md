# Secure Copying Files

Use the `scp` command that uses `ssh` underneath for copying to/from servers.

## File

### From local machine to server

```shell
scp myfile.txt server.host:./path/on/server/myfile.txt
```

### From server to local machine:

```shell
scp server.host:./path/on/server/myfile.txt .
```

## Directories


### From local machine to server

```shell
scp -r mydir server.host:./path/on/server/mydir
```

### From server to local machine:

```shell
scp -r server.host:./path/on/server/mydir .
```
