# Rename Local branch

## To rename the current branch :-  

```bash
git branch -m <newname>
```

## To rename a branch while pointed to any branch :-

```bash
git branch -m <oldname> <newname>
```

-m is short for --move.

## To push the local branch and reset the upstream branch :-

```bash
git push origin -u <newname>
```

## To delete the remote branch :-

```bash
git push origin --delete <oldname>
```

##  to switch from your current local branch to a remote branch, you can do so using these steps:


1. **Fetch Remote Branches (Optional)**: It's a good practice to fetch the latest updates from the remote repository before switching to a remote branch. This ensures you have the latest information about all branches, including the one you want to switch to. Run:

   ```
   git fetch
   ```

2. **Switch to the Remote Branch**: To switch to a remote branch and create a new local branch based on it, you can use the following command:

   ```
   git checkout -b local-branch-name remote-name/branch-name
   ```

   For example, if you want to switch to a remote branch called "feature-branch" from the remote named "origin" and create a new local branch named "my-feature-branch," you would run:

   ```
   git checkout -b my-feature-branch origin/feature-branch
   ```

   This command creates a new local branch (`my-feature-branch`) based on the remote branch (`origin/feature-branch`) and switches to it.

3. **Work on the Local Branch**: You can now work on the local branch you've created (`my-feature-branch`). Make your changes, commit them, and perform any other necessary operations.

Remember that this process involves creating a new local branch based on the remote branch. If you simply want to switch to an existing local branch that tracks a remote branch, you can use the `git checkout` command without the `-b` flag:

```
git checkout local-branch-name
```

If the local branch doesn't exist yet, but there's a corresponding remote branch, Git will create the local branch and set it to track the remote branch automatically.

As always, Git's behavior might vary based on the version you're using, so make sure to consult the official documentation or use `git --help` for the most accurate and up-to-date information.