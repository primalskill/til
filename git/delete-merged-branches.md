# Delete Merged Branches

There's a difference between local and remote branches. See how to view both here: [Show merged branches](git/merged-branches.md).

## ⚠ WARNING: These commands can destroy your Git repo and delete your files.

### Delete local branches that are merged into `main`

```shell
git branch --merged main | grep -v "^\* main" | xargs -n 1 -r git branch -d
```

- `git branch --merged main` shows the merged branches into `main`.
- `grep -v "^\* main"` remove any branch named `main`, `-v` means a negative match.
- `xargs -n 1 -r` build the command with arguments, `-n 1` max arguments that is accepted, `-r` do not run if there are no arguments.
- `git branch -d` delete the specified branch.

### Delete remote branches that are merged into `origin/main`

```shell
git branch -r --merged origin/main | grep -v main | grep "origin/" | cut -d "/" -f 2- | xargs -n 20 git push --delete origin
```

- `git branch -r --merged origin/main` shows the remote branches that are merged into `origin/main`.
- `grep -v main` remove any branch named `main`, `-v` means a negative match.
- `grep "origin/" select only branches starting with "origin/", so on the `origin` remote only.
- `cut -d "/" -f 2-` drop the `origin` prefix.
- `xargs -n 20` use at most 20 arguments per command line.
- `git push --delete origin` delete the branches on `origin`.
