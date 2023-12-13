# Documenting a Hotfix Release in Git

**Note:** This documentation assumes you have **not yet committed your bug fix**. If you have already committed your changes, follow the standard release process but use the `hotfix-*` naming convention.


## Step 1: Create a hotfix branch
Your first step is to create a hotfix branch from the `trunk` branch. The hotfix branch should be named `hotfix-v` followed by the targeted release version number.

Note that the third decimal place is used to denote a hotfix release.

**Example:** `hotfix-v2.5.1`

To create the hotfix branch from the *trunk* branch run the following git
commands:

```bash
git checkout -b hotfix-v2.5.1 trunk
git push --set-upstream origin hotfix-v2.5.1
```

## Step 2: Commit your bug fixes
Now is the time to commit your bug fixes to the hotfix branch. Make sure you also bump the version number and make any other changes needed before release.

Use as many commits as needed.

Make sure to commit your changes to the hotfix branch. A *git status* check should return clean.

**Note for .NET applications:** Again, because of the nature of local .NET application development environments, a git status may not be clean (i.e. you may have an altered web.config that shouldn't be committed, but you don't want to lose changes to).

## Step 3: Open a Pull Request from the Hotfix Branch to the Trunk Branch
Now that you got your release branch completed it's time to merge those changes back with `trunk` via a pull request!

1. On github.com, open the repositiory you are working with
1. Go to the Pull Requests tab
1. Click 'New pull request'
1. Set 'base' as `trunk`, and 'compare' as the release branch (aka `hotfix-v1.1.1`), and click 'Create pull request'
1. Include an informative title, notes on what changed, and set 'Assignees' as yourself
1. Create pull request

**Repeat Step 3 for any open Release branches!** - we need to make sure this hotfix makes it's way everywhere it needs to go. (More research needed on best practices here!)

## Step 4: Merge the Pull Request
Approve the pull request, and delete the Hotfix Branch via the GitHub.com interface.

## Step 5: Tag the release
1. Go to the repository you are working with on GitHub.com, and click 'Releases' on the right sidebar
1. Click 'Draft a new release'
1. Open the 'Choose a tag' menu, type in the version number, starting with a 'v' (aka `v1.1.1`), and choose 'create a new tag'
1. Title the release the same way
1. Include notes about what was fixed or changed during the release. You can generate these automatically based on commits by using the 'Generate release notes' button!
1. Click 'Publish release'

## Step 6: Deploy to Production
If a CI/CD tool is being used, this should kick off as soon as the merge to `trunk` is complete. 

Otherwise, deploy to production manually as soon as you are done - the `trunk` branch should always match production!