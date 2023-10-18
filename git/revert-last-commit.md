# Revert Last Commit on Branch

Reverting commits that were accidentally pushed into the wrong branch. This will `checkout` the branch the commit is on, create a new branch without checkout then reset the current branch and revert the commit keeping the commit on the other branch.

```shell
git checkout <the branch the commit was pushed to>
git branch <my new branch name>
git reset --hard <sha of the commit>^
```

**NOTE**: Make sure to put the `^` to the end of the sha.
