# Show Merged Branches

### Show merged branches into the active branch

This will show only local branches.

```shell
git branch --merged
```

### Show merged branches into the `main` branch

This will show only local branches.

```shell
git branch --merged main
```

### Show remote branches merged into `main`

```shell
git branch --remotes --merged main
```

### Show all (local and remote) branches merged into `main`

```shell
git branch --all --merged main
```

---

### Refs

- https://git-scm.com/docs/git-branch
