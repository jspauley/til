# Update An Expired Access Token

It's best practice to set an expiry on personal access tokens. As a result, you
will likely need to regenerate and update personal access tokens from time to
time.

Once an access token has been generated / regenerated, you can update your local
Git configuration by running one of the commands below. Once you do, the next
time you perform any action with Git (clone, pull, push, etc), you'll be asked
to login again or provide your personal access token. 

### macOS

```bash
git config --global credential.helper osxkeychain
```

### Windows

```bash
git config --global credential.helper wincred
```
