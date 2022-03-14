# Command Line Rebase Branch On Main

There are many times when a branch will need to be rebased off `main`,
particularly when working on high velocity repositories. You can quickly rebase
on `main` with the following command:

```
git fetch origin main && git rebase origin/main
```

The branch can also be pushed to GitHub by including at the end of the above
command:

```
&& git push origin your_branch_name
```

It may also be neccessary to force push the branch after a rebase. This can
be done by adding `-f` to the end of the push command.
