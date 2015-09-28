# git.bellevuecollege.edu

This documentation contains information for working with the git repository host `git.bellevuecollege.edu`.

This repository host runs [Gitolite](http://gitolite.com/gitolite/).

## Request Access

This host uses ssh public / private key authentication. If you have not done so already you must generate this key pair. See
[Generate a SSH Key Pair for Authentication](ssh-generate-key-pair.md) for more information.

To request access to this repository host send the contents of your public key file to one or more of the following administrators.

* [Nicole Swan](mailto:nicole.swan@bellevuecollege.edu)
* [Terrence Adams](mailto:terrence.adams@bellevuecollege.edu)

**Note:** If you accidentally send your private key file you will be requested to generate a new key pair starting the process all over again. Don't do this.

## List Repositories

To get a list of all the repositories your account has access to run the following command.

```
ssh git@git.bellevuecollege.edu
```

**Note:** This can also be used to test if your key pair is working with the host.

## Cloning Repositories

You can clone repositories you have access to using the following syntax.

```
git clone git@git.bellevuecollege.edu:<repository name>
```

For example to clone the globals repository.

```
git clone git@git.bellevuecollege.edu:globals
```

## Gitolite Administration

The gitolite project maintains documentation for administration.

[Basic Administration]
(http://gitolite.com/gitolite/basic-admin.html)

[The "conf" file (conf/gitolite.conf)]
(http://gitolite.com/gitolite/conf.html)
