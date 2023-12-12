# Documenting an Application Release in Git

**Note:** This documentation assumes you have not completed a release and are in the early stages of releasing the final product. If you have already released the final product and committed those changes to git seek help as the process will change depending on the situation.

## Step 0 (before you start): Do Your Development in a Feature Branch, and open Pull Requests into a Release Branch

See [Git Development Workflow](dev-workflow.md) for details on how to commit your code in preparation for release.

In order for this workflow to function, make sure you are doing your development work in a Feature Branch. A Feature Branch is a new Branch in GitHub that is named after the feature you are creating. 
It is recommended to create your feature branch from the targeted Release branch (if available), or Trunk.

You can either create a feature branch locally:

```bash
git checkout -b my-cool-feature
```

Or you can create it on GitHub:
1. Open the associated Issue/Task in GitHub Projects
2. On the sidebar, click Open in New Tab
3. On the sidebar, under the Development heading, click 'Create a branch for this issue'
4. In your local environment, checkout the branch and pull

## Step 1: Create a release branch
The release branch should be created as early as possible; there isn't really an upside to waiting. It should be created from the *trunk* branch.
The release branch should be named "*release-v*" followed by the targeted release version number.

**Example:** *release-v2.5*

To create the release branch from the *trunk* branch run the following git
command.

~~~~
git checkout -b release-v2.5 trunk
~~~~

Alternativly, you can do this within GitHub in the Branches section.

## Step 2: Open 

## Step 3: Commit last minute updates
Now is the time to make any changes that may need to be completed before the release. Usually this only includes bumping the version number to the targeted release version, but could include other small changes including bug fixes.

Make sure to commit your changes to the release branch. A *git status* check should return clean.

**Note for .NET applications:** Again, because of the nature of local .NET application development environments, a git status may not be clean (i.e. you may have an altered web.config that shouldn't be committed, but you don't want to lose changes to).

**Note for projects that use build processes:** Step 3 is the perfect time to compile your Sass/SCSS stylesheets for production. We primarily use Gulp for this - running simply `gulp` from the command line will compile for production. For plugins that use the Create Guten Blocks framework, run `npm run build` instead. 

## Step 4: Merge the release branch with trunk branch
Now that you got your release branch completed it's time to merge those changes back with *trunk* so the *trunk* branch stays current with the latest release.

You can do this by running the following git commands. Don't forget to edit the release branch name to match your own.

~~~~
git checkout trunk
git merge --no-ff release-v2.5
~~~~

## Step 5: Tag the release
While still in the *trunk* branch you should create a tag to document the release. The tag name should start with the letter *v* for version followed by the targeted release number. You can create a tag for the release with the following command.

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
with the *dev* branch just like you did with *trunk*.

~~~~
git checkout dev
git merge --no-ff release-v2.5
~~~~

## Step 7: Delete your release branch
Now that you have merged your release branch back into the *trunk* and *dev*
branches you can safely discard it with the following command.

~~~~
git branch -d release-v2.5
~~~~

## Step 8: Push changes to server

~~~~
git push origin dev
git push origin trunk
git push origin refs/tags/v2.5
~~~~

## Step 9: Mark tag as GitHub Release (optional)
While tags will display as releases in GitHub, doing an official GitHub release will
better display release information, and allow for easier access to release files.

1. Visit GitHub repository, select 'Releases', and select 'Draft new release'
2. In the 'Tag version' dropdown, select the tag created in Step 5, on the Trunk branch.
3. In the Release Title, add your tag name (aka 'v2.5')
4. In the Release Description, place the release notes (contents of the tag you created in Step 5)
5. If your application has a compiled form neccessary for install, you can upload it under 'Attach Binaries'
6. Publish Release
