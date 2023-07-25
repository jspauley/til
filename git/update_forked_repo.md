# Update A Forked Repo

If you have forked a repo, and the original now includes changes you'd like to have in your copy, you can pull in the latest version of the original repo using `git rebase`. To do so, run the following commands from your `main` branch:


First, add the original repo as an upstream source:

```bash
git remote add upstream https://github.com/original-source/repo-name.git
```

Next, fetch all of the remote branches from the upstream repo:

```bash
git fetch upstream
```

Now rebase your `main` branch on the `main` branch from the upstream repo:

```bash
git rebase upstream/main
```

And finally, force push your newly updated `main` branch back to GitHub:

```bash
git push origin main -f
```
