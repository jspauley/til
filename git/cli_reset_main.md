# Command Line Reset The Main Branch

There are times when the `main` branch will end up in a weird state and need to be reset.
In particular, this happens if a commit is created on `main` before being added to a separate
branch and merged. You can quickly reset `main` by running the following command:

```bash
git reset --hard origin/main
```

The local `main` branch will now be reset to the state of the remote `main` branch.
