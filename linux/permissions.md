# Linux Permissions

![image](https://github.com/primalskill/til/assets/489775/f3aa9095-ff65-4c37-ae76-55b1a671557d)

## Changing Owner

```shell
chown someuser:somegroup file.txt
```

### Recursive owner change

```shell
chown -R someuser:somegroup path/to/folder
```

## Changing Permissions

Pattern: `<ugo>+-<rwx>`

- First part: `ugo` are identifiers for `u` - **u**ser, `g` - **g**roup, `o` - **o**ther
- Second part: `+-` are identifiers for `+` - add permission, `-` - remove permission
- Third part: `rwx` are identifiers for `r` - **r**ead, `w` - **w**rite, `x` - e**x**ecute

### Add read, write, execute permissions to user

```shell
chmod u+rwx file.txt
```

### Remove execute permission from user

```shell
chmod u-x file.txt
```

### Add read and execute permissions to group and other

```shell
chmod go+rx file.txt
```

### Remove execute permissions from other

```shell
chmod o-x file.txt
```

### Recursive permission change

Add the `-R` after chmod.

```shell
chmod -R u+r path/to/folder
```
