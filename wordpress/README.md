# WordPress Tips and Tricks
How to fix odd things that we haven't found solutions for elsewhere.

## User can not be added to site

### Issue:

* User exists at the network level
* User does not show as existing at the site level
* When you attempt to use Add Existing User to add user to site, a message is displayed that the user already exists

### How to fix:

This requires editing the WordPress database. The issue occurs because the user exists on the site, but has **no role assigned**. 

You need two pieces of information to fix this issue.

1. User ID: Edit user on the Network Dashboard, and collect user ID from the URL
1. Site ID: Edit the site from the Network Dashboard, and collect site ID from the URL

Take the following steps:

1. Open the `wp_usermeta` table in phpmyadmin
1. Go to Search tab
1. Put User ID in the `user_id` search field
1. Put wp_{User ID}% in the `meta_key` search field
   * for example, if your Site ID is 20, put in `wp_20%`
1. This should surface a row with the `meta_key` of wp_{User ID}_capabilities (such as `wp_20_capabilities`). You'll notice that the `meta_value` of this is `a:0:{}`.
1. Delete this row

Once this row is deleted, you may need to clear your object cache (for example purge memcached) to make sure that WordPress can see the changes. 

That's all, folks!