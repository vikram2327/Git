# GO back to specific commit and delelte all the comit after that from local 
To go back to a specific commit and delete all the commits after that from your local repository, you can follow these steps:

1. **Check Your Current Branch:** First, ensure that you are on the branch from which you want to delete the commits. You can check your current branch by running:

   ```
   git branch
   ```

   This will list all the branches, and the currently checked-out branch will be highlighted with an asterisk (*).

2. **Identify the Commit to Go Back To:** Find the specific commit hash to which you want to reset your branch. You can use `git log` to view the commit history and find the hash of the commit you want to go back to.

3. **Reset to the Specific Commit:** Use the `git reset` command to reset your branch to the desired commit. Replace `<commit-hash>` with the actual hash of the commit you want to go back to:

   ```
   git reset --hard <commit-hash>
   ```

   This command will move your branch pointer and the working directory back to the specified commit. The `--hard` flag means that it will discard all changes made after that commit.

4. **Delete the Remote Branch (Optional):** If you want to remove the commits from the remote repository as well, you can force push the branch to update it on the remote server. Be cautious when using `git push --force`, as it rewrites the commit history on the remote repository and can potentially cause issues for other collaborators. Replace `<branch-name>` with the name of your branch:

   ```
   git push --force origin <branch-name>
   ```

   Please use this step with caution and only if you are the only person working on the branch or have coordinated with your team.

Now, your local branch should be at the specific commit you selected, and all commits after that commit should be removed. Please be very cautious when using `git reset --hard` and `git push --force` because they can result in permanent data loss if not used carefully.