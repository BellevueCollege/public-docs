# Documenting a Hotfix Release in Git

This documentation is based on the [A Successful Git Branching Model]
(http://nvie.com/posts/a-successful-git-branching-model/) web page from the **Release branches** section.

**Note:** This documentation assumes you have **not yet committed your bug fix**. If you have already committed your changes, follow the standard release process but use the `hotfix-*` naming convention.

## Step 1: Make sure you don't have any commits left in dev and master branch.
Make sure the `dev` and `master` branches are up to date with the server.

####PHP application
*Warning:* This will destroy any commits that were not pushed to the git upstream server aliased as *origin*.

~~~~
git checkout dev
git fetch origin dev
git reset --hard FETCH_HEAD

git checkout master
git fetch origin master
git reset --hard FETCH_HEAD
~~~~

####.NET application

As .NET applications often have config files specific to local development or other environment artifacts, it is not recommended to do a hard reset, but you can still do a fetch to make sure there are not any upstream changes you don't have in your local git repo.

~~~~
git checkout dev
git fetch origin dev

git checkout master
git fetch origin master
~~~~

## Step 2: Create a hotfix branch
Your first step is to create a hotfix branch from the *master* branch. The hotfix branch should be named "*hotfix-v*" followed by the targeted release version number.

Note that the third decimal place is used to denote a hotfix release.

**Example:** *hotfix-v2.5.1*

To create the hotfix branch from the *trunk* branch run the following git
command.

~~~~
git checkout -b hotfix-v2.5.1 trunk
~~~~

## Step 3: Commit your bug fixes
Now is the time to commit your bug fixes. Make sure you also bump the version number and make any other changes needed before release.

Use as many commits as needed.

Make sure to commit your changes to the hotfix branch. A *git status* check should return clean.

**Note for .NET applications:** Again, because of the nature of local .NET application development environments, a git status may not be clean (i.e. you may have an altered web.config that shouldn't be committed, but you don't want to lose changes to).

## Step 4: Merge the hotfix branch with master branch
Now that you've got your hotfix branch completed it's time to merge those changes back with *master* so the *master* branch stays current with the latest release.

You can do this by running the following git commands. Don't forget to edit the hotfix branch name to match your own.

~~~~
git checkout trunk
git merge --no-ff hotfix-v2.5.1
~~~~

## Step 5: Tag the release
While still in the *trunk* branch you should create a tag to document the release. The tag name should start with the letter *v* for version followed by the targeted release number. You can create a tag for the release with the following command.

~~~~
git tag -a v2.5.1
~~~~

After running this command you will be prompted to add a message to the tag. We use this message to capture the changelog from within git. Use the following template to create your changelog message for the tag.

~~~~
Hotfix release of version 2.5.1

Updates since v2.5
------------------

* Fixed this
* Updated that
* Added this
~~~~

## Step 6: Merge hotfix with the dev branch
Finally we will want to make sure changes that happened in the hotfix branch make it back to the *dev* branch. You will want to merge your hotfix branch with the *dev* branch just like you did with *master*.

~~~~
git checkout dev
git merge --no-ff hotfix-v2.5.1
~~~~

## Step 7: Delete your hotfix branch
Now that you have merged your hotfix branch back into the *master* and *dev* branches you can safely discard it with the following command.

~~~~
git branch -d hotfix-v2.5.1
~~~~

## Step 8: Push changes to server

~~~~
git push origin dev
git push origin trunk
git push origin refs/tags/v2.5.1
~~~~

## Step 9: Mark tag as GitHub Release (optional)

While tags will display as releases in GitHub, doing an official GitHub release will better display release information, and allow for easier access to release files.

1. Visit GitHub repository, select 'Releases', and select 'Draft new release'
2. In the 'Tag version' dropdown, select the tag created in Step 5, on the Master branch.
3. In the Release Title, add your tag name (aka 'v2.5')
4. In the Release Description, place the release notes (contents of the tag you created in Step 5)
5. If your application has a compiled form neccessary for install, you can upload it under 'Attach Binaries'
6. Publish Release
