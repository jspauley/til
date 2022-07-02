# Changing Multiple Commits

While it's simple enough to [change the last commit](git/change_last_commit.md),
there are times when the solution involves editing or squashing multiple commits.
This can be accomplished with an interactive rebase by running the following
command, where the number is how many commits back in time you'd like to edit:

```
git rebase -i HEAD~3
```

This will bring up a list of the last three commits along with an option next to 
each of them (the default being `pick`). Now you can select which ones to keep
and which ones to squash (or perform other actions on) by marking an `s` or 
`squash` or other commands next to the appropriate commits. Because this defaults 
to openinig and editing in Vim, use `:x return` to save your changes. 

Once that's done you'll be present with a list of the commit messages, where you 
similarly are giving the option of which to keep by commenting out the unneeded lines.
That's it! Once finished the branch can be pushed to GitHub by running:

```
git push origin your_branch_name
```

It may also be neccessary to force push the branch given that this was a rebase. 
This can be done by adding `-f` to the end of the push command.
