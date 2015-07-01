# Installing Git in Windows

This file contains git installation information that is specific to the
Microsoft Windows operating system platform.

## Download

Download the latest copy of git from the
[Downloads Section](https://git-scm.herokuapp.com/downloads) on the
official website.

## Install

Execute the git installation file to install git. At the time of this writing
we use the default installation settings.

**TODO:** Add installation specific settings.

## Configuration Files

The **.gitconfig** file and **.ssh\\** directory will both be located in your user
folder under **C:\Users**. Neither one of these files may yet exist if you are
working with a fresh installation.

Other parts of this documentation may reference this file and folder.

## Git BASH

The default git command prompt in Windows is the git BASH prompt. When you are
instructed to run git commands or run something from the "command prompt" this
is in reference to the git BASH prmpt unless you have set up an alternative
(such as posh-git).

## posh-git

posh-git makes git work in PowerShell which generally is easier to work with
than the default git BASH prompt. You can download posh-git from the
[official website](https://dahlbyk.github.io/posh-git/).

**TODO:** [posh-git Installation Instructions]
(git-installation-windows-posh-git.md)

## Commit Message Editor

Many people prefer to use a text editor of their preference for composing commit
messages.

It is strongly recommended you choose an plain text editor that displays line
character counts, or one that supports hard line wrapping at 72 characters. This
is important for writing commit messages with the 50/72 style.

### Notepad++

Notepad++ is a popular choice and displays line character counts.

If Notepad++ is not already installed you will need to download and install it
from the [official website](http://notepad-plus-plus.org/).

To set Notepad++ as your commit message editor run the following command. You
may need to adjust the path to Notepad++ if it is installed in a different
directory.

```
$ git config --global core.editor "'C:/Program Files (x86)/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"
```
