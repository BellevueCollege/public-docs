# Recommended Developer Workflow

As of December 2023, the recommended developer workflow has changed from 'git flow' to a release-focused varation of [GitHub Flow](https://docs.github.com/en/get-started/quickstart/github-flow).

This workflow is focused on Pull Requests, which you can initiate easily from within GitHub. A Pull Request documents that you are ready to move your code into production, and allows that code
to be tested before it is released. This is particularly easy when things are configured for continuous integration and delivery.

## The Essential Workflow:
1. Create a **Release Branch** from `trunk` as soon as you start planning a release. Naming should be `release-vX.X.X` or `hotfix-vX.X.X`, using the targeted version number.
1. Create a **Feature Branch** from the release branch (or `trunk`) as soon as you start working on a feature/issue. It should be named something related to the issue, and not use 'release' or 'hotfix' in the name.
1. When the feature or issue is complete, open a Pull Request *from* the feature branch *to* the release branch
1. Fix any bugs in the same feature branch- the pull request will automatically update
1. When all bugs are resolved, approve the pull request. This will merge it into the release branch.
1. Follow this process for all issues/features targeted for the release
1. Prepare for the release (once all desired pull requests are merged):
   1. Make any final updates to the Release Branch (aka bump version number, etc)
   1. Open a Pull Request *from* the Release Branch *to* `trunk`
1. Merge the pull request to `trunk`
1. Create a new Release in GitHub, tagging it with the version number (aka `v1.1.1`), and including release notes
1. Deploy code to production (if needed)

Having trouble visualizing this? [Here's a diagram!](commit-flow-diagram.png)


## Details for Each Step

### Step 1: Create a Release Branch
The release branch should be created as early as possible; there isn't really an upside to waiting. It should be created from the *trunk* branch.

The release branch should be named "*release-v*" followed by the targeted release version number.

**Example:** *release-v2.5*

To create the release branch from the *trunk* branch run the following git
command, which creates a new branch and pushes it to github:

```bash
git checkout -b release-v2.5 trunk
git push --set-upstream origin release-v2.5
```

Alternativly, you can do this within GitHub in the Branches section.

### Step 2: Create a Feature Branch
In order for this workflow to function, make sure you are doing your development work in a Feature Branch. A Feature Branch is a new Branch in GitHub that is named after the feature you are creating. 

It is recommended to create your feature branch from the targeted Release branch (if available), or `trunk`.

You can either create a feature branch locally:

```bash
git checkout -b my-cool-feature
git push --set-upstream origin my-cool-feature
```

Or you can create it on GitHub:
1. Open the associated Issue/Task in GitHub Projects
2. On the sidebar, click Open in New Tab
3. On the sidebar, under the Development heading, click 'Create a branch for this issue'
4. In your local environment, checkout the branch and pull

Make sure you commit and push code to the feature branch regularly!

### Step 3: Open a Pull Request for your Feature
A 'Pull Request' is the way you 'ask' to merge your feature into the Release branch. This is when QA testing and bug fixes take place.

1. On github.com, open the repositiory you are working with
1. Go to the Pull Requests tab
1. Click 'New pull request'
1. Set 'base' as the release branch, and 'compare' as your feature branch, and click 'Create pull request'
1. Include an informative title, notes on what changed, and set 'Assignees' as yourself, and 'Reviewers' to whoever will be QA'ing your code.
1. Create pull request
1. Deploy code to test (if needed)

### Step 4: Review and Bug Fixes

Putting in the pull request will trigger CI/CD processes (where available). QA will test the contents of the pull request, and report bugs
via GitHub projects. 

Bug fixes should be committed and pushed to the feature branch- the pull request will update automatically.

Fixed bugs should be assigned back to QA in GitHub Projects, and moved to the 'In Testing' status.

QA will approve the pull request once review is complete, and move all associated issues to 'Ready for Release'.

### Step 5: Approve the Pull Request

Once review is complete and all bugs fixed, merge the pull request and delete the feature branch. This can be done from the github.com interface.

### Step 6: Repeat for All Features in Release

Often a release will include several features, bug fixes, etc, and so may include multiple pull requests. Do not proceed with the release until all pull requests are merged!

### Step 7 through 10: Release!
See the [application release instructions](git-application-release.md) for details
