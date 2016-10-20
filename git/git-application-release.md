# Documenting an Application Release in Git

This documentation is based on the [A Successful Git Branching Model]
(http://nvie.com/posts/a-successful-git-branching-model/) webpage from the **Release branches** section.

**Note:** This documentation assumes you have not completed a release and are in the early stages of releasing the final product. If you have already released the final product and committed those changes to git seek help as the process will change depending on the situation.

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

## Step 2: Create a release branch
Your first step is to create a release branch from the *dev* branch. The
release branch should be named "*release-v*" followed by the targeted release version number.

**Example:** *release-v2.5*

To create the release branch from the *dev* branch run the following git
command.

~~~~
git checkout -b release-v2.5 dev
~~~~

## Step 3: Commit last minute updates
Now is the time to make any changes that may need to be completed before the release. Usually this only includes bumping the version number to the targeted release version, but could include other small changes including bug fixes.

Make sure to commit your changes to the release branch. A *git status* check should return clean.

**Note for .NET applications:** Again, because of the nature of local .NET application development environments, a git status may not be clean (i.e. you may have an altered web.config that shouldn't be committed, but you don't want to lose changes to).

## Step 4: Merge the release branch with master branch
Now that you got your release branch completed it's time to merge those changes back with *master* so the *master* branch stays current with the latest release.

You can do this by running the following git commands. Don't forget to edit the release branch name to match your own.

~~~~
git checkout master
git merge --no-ff release-v2.5
~~~~

## Step 5: Tag the release
While still in the *master* branch you should create a tag to document the release. The tag name should start with the letter *v* for version followed by the targeted release number. You can create a tag for the release with the following command.

~~~~
git tag -a v2.5
~~~~

After running this command you will be prompted to add a message to the tag. We use this message to capture the changelog from within git. Use the following template to create your changelog message for the tag.

~~~~
Production release of version 2.5

Updates since v2.4
------------------

* Fixed this
* Updated that
* Added this
~~~~

## Step 6: Merge release with the dev branch
Finally we will want to make sure changes that happened in the release branch
make it back to the *dev* branch. You will want to merge your release branch
with the *dev* branch just like you did with *master*.

~~~~
git checkout dev
git merge --no-ff release-v2.5
~~~~

## Step 7: Delete your release branch
Now that you have merged your release branch back into the *master* and *dev*
branches you can safely discard it with the following command.

~~~~
git branch -d release-v2.5
~~~~

## Step 8: Push changes to server

~~~~
git push origin dev
git push origin master
git push origin refs/tags/v2.5
~~~~
