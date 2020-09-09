# Renaming the Primary Git Branch to Trunk

Currently many repositories use a 'Master' and 'Dev' branch system instead of 'Trunk' and 'Dev'.
The Trunk terminology was decided on to fit with the tree imagery present in Git. GitHub is moving defaults to 'Main', but using 'Trunk' should not cause conflict.

When you update an application, please update branch names if possible. 

## Directions

Adapted from https://dev.to/rhymu8354/git-renaming-the-master-branch-137b

1. Rename your local branch. `git branch -m master trunk`
2. Push renamed branch upstream and set remote tracking branch. `git push -u origin trunk`
3. Log into GitHub and change the "default branch"
   1. Go to the Repository, and open the repository Settings
   2. Go to Branches
   3. Set 'trunk' as the primary branch
4. Delete the old branch upstream. `git push origin --delete master`
5. Update the upstream remote's HEAD. `git remote set-head origin -a`

That's covers it on your end and where your repository is hosted. Now what do you have to do if it's someone else's repo which renamed a branch, and you're left holding a "dangling" reference (so to speak) to a remote branch that no longer exists?

If you know the branch was renamed, there's nothing to fear. The following steps will get you back on track:

1. Fetch the latest branches from the remote. `git fetch --all`
2. Update the upstream remote's HEAD. `git remote set-head origin -a`
3. Switch your local branch to track the new remote branch. `git branch --set-upstream-to origin/trunk`
4. Rename your branch locally. `git branch -m master trunk`
