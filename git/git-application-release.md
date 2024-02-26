# Documenting an Application Release in Git

**Note:** This documentation assumes you have not completed a release and are in the early stages of releasing the final product. If you have already released the final product and committed those changes to git seek help as the process will change depending on the situation.

## Step 0 (before you start): Do Your Development in a Feature Branch, and open Pull Requests into a Release Branch

See [Git Development Workflow](dev-workflow.md) for details on how to commit your code in preparation for release.

## Step 1: Make sure you are on the Release Branch
The release branch should be called something like `release-v1.1`, and include any changes targeted for this release. 

## Step 2: Commit last minute updates
Now is the time to make any changes that may need to be completed before the release. Usually this only includes bumping the version number to the targeted release version, but could include other small changes including bug fixes.

Make sure to commit your changes to the release branch. A *git status* check should return clean.

**Note for .NET applications:** Because of the nature of local .NET application development environments, a git status may not be clean (i.e. you may have an altered web.config that shouldn't be committed, but you don't want to lose changes to).

**Note for projects that use build processes:** Step 3 is the perfect time to compile your Sass/SCSS stylesheets for production. We primarily use Gulp for this - running simply `gulp` from the command line will compile for production. For plugins that use a different framework, run the appropriate command instead. 

## Step 3: Open a Pull Request from the Release Branch to the Trunk Branch
Now that you got your release branch completed it's time to merge those changes back with `trunk` via a pull request!

1. On github.com, open the repositiory you are working with
1. Go to the Pull Requests tab
1. Click 'New pull request'
1. Set 'base' as `trunk`, and 'compare' as the release branch (aka `release-v1.1`), and click 'Create pull request'
1. Include an informative title, notes on what changed, and set 'Assignees' as yourself, and 'Reviewers' to whoever will be QA'ing your code (if another QA pass is needed).
1. Create pull request
1. Deploy code to test again (if needed)

## Step 4: Merge the Pull Request
Approve the pull request, and delete the Release Branch via the GitHub.com interface.

## Step 5: Tag the release
1. Go to the repository you are working with on GitHub.com, and click 'Releases' on the right sidebar
1. Click 'Draft a new release'
1. Open the 'Choose a tag' menu, type in the version number, starting with a 'v' (aka `v1.1`), and choose 'create a new tag'
1. Title the release the same way
1. Include notes about what was fixed or changed during the release. You can generate these automatically based on commits by using the 'Generate release notes' button!
1. Click 'Publish release'

## Step 6: Deploy to Production
If a CI/CD tool is being used, this should kick off as soon as the merge to `trunk` is complete. 

Otherwise, deploy to production manually as soon as you are done - the `trunk` branch should always match production!