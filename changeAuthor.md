## Using Rebase
First, if you haven't already done so, you will likely want to fix your name in git-config:

```
git config --global user.name "New Author Name"
git config --global user.email "<email@address.example>"
```
This is optional, but it will also make sure to reset the committer name, too, assuming that's what you need.

To rewrite metadata for a range of commits using a rebase, do

```
git rebase -r <some commit before all of your bad commits> \
    --exec 'git commit --amend --no-edit --reset-author'
```
--exec will run the git commit step after each commit is rewritten (as if you ran git commit && git rebase --continue repeatedly).

If you also want to change your first commit (also called the 'root' commit), you will have to add --root to the rebase call.

This will change both the committer and the author to your user.name/user.email configuration. If you did not want to change that config, you can use --author "New Author Name <email@address.example>" instead of --reset-author. Note that doing so will not update the committer -- just the author.

### Single Commit
If you just want to change the most recent commit, a rebase is not necessary. Just amend the commit:

 git commit --amend --no-edit --reset-author
### Entire project history
git rebase -r --root --exec "git commit --amend --no-edit --reset-author"
### For older Git clients (pre-July 2020)
-r,--rebase-merges may not exist for you. As a replacement, you can use -p. Note that -p has serious issues and is now deprecated.

## Refrence
- https://stackoverflow.com/questions/750172/how-do-i-change-the-author-and-committer-name-email-for-multiple-commits