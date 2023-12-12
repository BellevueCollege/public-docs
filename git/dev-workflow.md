# Recommended Developer Workflow

As of December 2023, the recommended developer workflow has changed from 'git flow' to a release-focused varation of [GitHub Flow](https://docs.github.com/en/get-started/quickstart/github-flow).

This workflow is focused on Pull Requests, which you can initiate easily from within GitHub. A Pull Request documents that you are ready to move your code into production, and allows that code
to be tested before it is released. This is particularly easy when things are configured for continuous integration and delivery.

## The Essential Workflow:
1. Create a **Release Branch** from `trunk` as soon as you start planning a release. Naming should be `release-vX.X.X` or `hotfix-vX.X.X`, using the targeted version number.
1. Create a **Feature Branch** from the release branch (or `trunk`) as soon as you start working on a feature/issue. It should be named something related to the issue, and not use 'release' or 'hotfix' in the name.
1. Commit and push to the feature branch frequently
1. When the feature or issue is complete, open a Pull Request *from* the feature branch *to* the release branch
1. Set QA as the Reviewer for the pull request, and deploy to the QA environment if needed
1. QA will test the contents of the pull request, and report any bugs.
1. Fix any bugs in the same feature branch- the pull request will automatically update
1. When all bugs are resolved, approve the pull request. This will merge it into the release branch.
1. Follow this process for all issues/features targeted for the release
1. Prepare for the release (once all desired pull requests are merged):
  1. Make any final updates to the Release Branch (aka bump version number, etc)
  1. Open a Pull Request *from* the Release Branch *to* `trunk`
  1. If neccessary, have QA review this for any integration issues
1. Merge the pull request to `trunk`
1. Create a new Release in GitHub, tagging it with the version number (aka `v1.1.1`), and including release notes
1. Deploy code to production (if needed)
