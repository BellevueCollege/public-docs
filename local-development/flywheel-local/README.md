# Setting up Local by Flywheel
Local is a free GUI local development environment system. These are recommended configurations for a system to match BC's production environment. 

Local is available for Mac and PC at <https://local.getflywheel.com/>

## Setup
Flywheel should be installed and fully set up before following these directions. 

### Install Plugin to Allow Mapped Directories
It is best to map in directories for plugins and themes, so that they can be stored in a central location. The [Local Addon Volumes](https://github.com/getflywheel/local-addon-volumes) plugin allows this to be easily configured. Note that this add on has only been tested on Mac.

1. Download plugin from <https://github.com/getflywheel/local-addon-volumes>
2. In Local, open **Preferences**
3. On the sidebar, select **Add-Ons**
4. Select **Install Add-On**
5. Select .zip file downloaded in step 1
6. Turn on add-on. 

### Set up VM

1. Click + to add new site
2. Enter site name (eg Local Multisite), and then Continue
3. Under **Choose Your Environment** select **Custom**
   * PHP Version 5.3.x
   * Web Server: nginx
   * MySQL Version: 5.6
4. Set an easy to remember username and password
5. Click 'Add Site'

### Map Directories

1. Once site is set up, under your site settings, select **More**, then **Volumes**
2. For each directory to map in, select it under **Add Host Source**
3. Type the desired container destination (themes are under /app/public/wp-content/themes/, plugins under /app/public/wp-content/plugins)

#### Example Mayflower on Mac

   ```
   HOST: /Users/taija.tevia-clark/GitProjects/mayflower
   CONTAINER: /app/public/wp-content/themes/mayflower
   ```
