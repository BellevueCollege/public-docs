# Git

Git is a distributed version control system. If you would like to read more
about git there are many good online resources, a few of which are listed below.

* [Pro Git Book](https://git-scm.herokuapp.com/book/)
* [GitHub Interactive Git Tutorial](https://try.github.io/)
* [Introduction to Git with Scott Chacon]
  (https://www.youtube.com/watch?v=ZDR433b0HJY)
* [Git Learning Videos](https://git-scm.herokuapp.com/videos)
* [Git Reference Documentation](https://git-scm.herokuapp.com/docs)

## Recommended Workflow
- [Developer Workflow](dev-workflow.md) - [Diagram of Workflow](dev-workflow.png)
- [Documenting an Application Release in Git](git-application-release.md)
- [Documenting a Hotfix Release in Git](git-hotfix-release.md)

## Installation

Git supports multiple platforms. Downloads and be found from the [official
website](https://git-scm.com/).

* [Windows Installation](git-installation-windows.md)
* [OS X Installation](git-installation-osx.md)

## Setting Author Information

On each new system you use/install git you will want to set your personal
author information. You can do so by running the following commands replacing
the generic name and email information with your own.

```
git config --global user.name "Firstname Lastname"
git config --global user.email "your.email@bellevuecollege.edu"
```

## Commit Message Style

We use [Tim Pope's recommended "50/72 style"](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html) for commit messages.

The blog post is fairly informative but the highlights are:

* Commit messages should be written in the imperative: "Fix bug" and not "Fixed
  bug"
* First line of your commit message should be treated as a subject line
    * Subject lines are mandatory for commit messages
    * Subject lines should be no longer than 50 characters
    * Subject lines should capitalized as if they were titles
* Second line of your commit message should be a single new line character
* The third line of your commit message should be treated as the commit message
  body
    * Commit message bodies are optional for commit messages
    * Commit message body lines should not exceed 72 characters

### More Dynamic Commit Messages
* To add some excitement to your commit messages, you can use [Emoji Log style commits 🚀](https://github.com/ahmadawais/Emoji-Log/).

## Branch Names

All Git repositories should have the following branch at minimum:

* **trunk** - should ALWAYS match what is in production

### Removing 'Master' terminology

Currently many repositories use a 'Master' and 'Dev' branch system instead of 'Trunk' and 'Dev'.
The Trunk terminology was decided on to fit with the tree imagery present in Git. GitHub is moving defaults to 'Main', but using 'Trunk' should not cause conflict.

When you update an application, please update branch names if possible. [Directions on updating the Master branch name](rename-git-branch.md).

### The 'Dev' branch

Currently many responsitories still use the 'git flow' based workflow, which depends on a Dev and Trunk branch instead of using a pull-request based workflow. 
It is recommended to switch over to the GitHub Flow + Releases workflow instead.

## Repository Hosts

We use one repository host:
- [GitHub](https://github.com/bellevuecollege)

* [GitHub Documentation](git-host-github.md)

## Helpful GUI Clients

While comfort with the command line is essential for git, 
there are some useful GUI applications that allow for easier visualization
of branches and changes. 

* [GitHub Application](https://desktop.github.com/) - Cross Platform, GitHub Focused
* [GitX-dev](http://rowanj.github.io/gitx/) - OSX Client
* [Visual Studio Code](https://code.visualstudio.com/) has a great built in mergetool to assist with conflicts
* If you use VS Code, [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) offers a ton of useful tools.

## Other Documentation

[Generate a SSH Key Pair for Authentication](ssh-generate-key-pair.md)

