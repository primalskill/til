# Available Space in Directory

## Simple

Not very usable though. Dumps the current directory size and the immediate directories in it.

```shell
du -h .
```

## Sort by size

```shell
du -h . | sort -rh
```

## Show the top 10 largest directories

```shell
du -h . | sort -rh | head -n 10
```
