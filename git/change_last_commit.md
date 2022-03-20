# Changing The Last Commit

There are times when it's preferable to edit a commit rather than adding a whole
new one, particularly in some high velocity repositories where the goal is to
have one commit per pull request. In such cases, a single commit can be edited
any time we have new changes using the following command:

```
git commit --amend
```

This will also prompt for any changes to the commit message, while amending the
commit.

If you want to keep the same commit message, but just update the code changes,
you can use the following command:

```
git commit --amend --no-edit
```

In either case, a force push of the branch will be required if this commit was
previously pushed to GitHub. This can be done by running:

```
git push origin your_branch_name -f
```
