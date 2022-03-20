# Changing Multiple Commits

While it's simple enough to [change the last commit](git/change_last_commit.md),
there are times when the solution involves editing or squashing multiple commits.
This can be accomplished with an interactive rebase by running the following
command, where the number is how many commits back in time you'd like to edit:

```
git rebase -i HEAD~3
```

You'll then be presented with the last three commits, and a series of options
for editing them. You'll also be given a change to update the commit messages.
