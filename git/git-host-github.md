# GitHub

This documentation contains information for working with [GitHub]
(https://github.com/).

We mainly participate and interact with two GitHub organization accounts.

* [Bellevue College](https://github.com/BellevueCollege/)
* [Washington State CTC Developers](https://github.com/ctcdev)

## Request Access

Most repositories we work with on GitHub are public allowing you to clone
those repositories anonymously. Eventually though you will need to push your commits back to GitHub and access repositories that are not public.

To be granted elevated access to GitHub you must have an GitHub account. If you do not already have a GitHub account you would like to use, create one using the link below.

[Join GitHub](https://github.com/join)

After creating your account, send your username to one of the following
administrators.

* [Eden Lasater](mailto:eden.lasater@bellevuecollege.edu)
* [Nicole Swan](mailto:nicole.swan@bellevuecollege.edu)

## SSH Key Pair Authentication

It is recommended that you push and pull content from GitHub over SSH using public/private key authentication. If you have not done so already you should generate this key pair. See [Generate a SSH Key Pair for Authentication](ssh-generate-key-pair.md) for more information.

Once you have generated your SSH key pair you must upload your public key to GitHub. Follow GitHub's *Generating SSH keys* documentation starting at *Step 4*.

[Step 4: Add your SSH key to your account]
(https://help.github.com/articles/generating-ssh-keys/#step-4-add-your-ssh-key-to-your-account)

## Additional User Settings

Additionally you may wish to consider the following GitHub documentation to further configure your account.

* [Adding an email address to your GitHub account]
  (https://help.github.com/articles/adding-an-email-address-to-your-github-account/)
* [Verifying your email address]
  (https://help.github.com/articles/verifying-your-email-address/)
* [Publicizing or concealing organization membership]
  (https://help.github.com/articles/publicizing-or-concealing-organization-membership/)
* [Configuring two-factor authentication via a TOTP mobile app]
  (https://help.github.com/articles/configuring-two-factor-authentication-via-a-totp-mobile-app/)
* [Configuring two-factor authentication via text message]
  (https://help.github.com/articles/configuring-two-factor-authentication-via-text-message/)
* [Make your password as strong as possible]
  (https://help.github.com/articles/what-is-a-strong-password/#make-your-password-as-strong-as-possible)

## Administration

### Add New Repositories to Bellevue College

The following settings should be adjusted accordingly for new repositories.

* The *Default branch* branch should be set to *dev* unless the repository does not use a *dev* branch.
    * [Setting the default branch]
      (https://help.github.com/articles/setting-the-default-branch/)
* The *Issues* and *Wiki* feature should be turned off unless the repository is specifically using these features.
    * [Disabling issues](https://help.github.com/articles/disabling-issues/)
    * [Disabling wikis](https://help.github.com/articles/disabling-wikis/)
* The *Integration* team should always be added as a collaborator.
    * [Adding collaborators to a personal repository]
      (https://help.github.com/articles/adding-collaborators-to-a-personal-repository/)

### Grant Access

Personnel of the Integration Team should always be added to the teams for the following GitHub organization accounts.

* Bellevue College
    * Integration
* Washington State CTC Developers
    * Members

If administration level access is needed then personnel should be added to the following additional accounts.

* Bellevue College
    * Owners
* Washington State CTC Developers
    * Owners

[Permission levels for an organization repository]
(https://help.github.com/articles/permission-levels-for-an-organization-repository/)
