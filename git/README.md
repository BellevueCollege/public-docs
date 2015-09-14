# Git

Git is a distributed version control system. If you would like to read more
about git there are many good online resources, a few of which are listed below.

* [Pro Git Book](https://git-scm.herokuapp.com/book/)
* [GitHub Interactive Git Tutorial](https://try.github.io/)
* [Introduction to Git with Scott Chacon]
  (https://www.youtube.com/watch?v=ZDR433b0HJY)
* [Git Learning Videos](https://git-scm.herokuapp.com/videos)
* [Git Reference Documentation](https://git-scm.herokuapp.com/docs)

## Installation

Git supports multiple platforms. Downloads and be found from the [official
website](https://git-scm.com/).

[Windows Installation](git-installation-windows.md)

**TODO:** [OS X Installation](git-installation-osx.md)

**TODO:** [Linux Installation](git-installation-linux.md)

## Setting Author Information

On each new system you use/install git you will want to set your personal
author information. You can do so by running the following commands replacing
the generic name and email information with your own.

```
git config --global user.name "Firstname Lastname"
git config --global user.email "your.email@bellevuecollege.edu"
```

## Commit Message Style

We use Tim Pope's recommend "50/72 style" for commit messages.

<http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html>

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

## Branching Model

We use a branching model based around Vincent Driessen's blog post
[A successful Git branching model]
(http://nvie.com/posts/a-successful-git-branching-model/)

**TODO:** [Git Branching Model Documentation](git-branch-model.md)

## Repository Hosts

We use two repository hosts, a local server running
[Gitolite](http://gitolite.com/gitolite/) hosted at git.bellevuecollege.edu, and
[GitHub](https://github.com).

[git.bellevuecollege.edu Documentation]
(git-host-git.bellevuecollege.edu.md)

[GitHub Documentation]
(git-host-github.md)

## Helpful GUI Clients

While comfort with the command line is essential for git, 
there are some useful GUI applications that allow for easier visualization
of branches and changes. 

* [GitHub Application](https://desktop.github.com/) - Cross Platform, GitHub Focused
* [GitX-dev](http://rowanj.github.io/gitx/) - OSX Client

## Other Documentation

[Generate a SSH Key Pair for Authentication](ssh-generate-key-pair.md)

[Documenting an Application Release in Git](git-application-release.md)
