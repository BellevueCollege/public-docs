#Setting Up Varying Vagrant Vagrants (VVV)
Varying Vagrant Vagrants (VVV) is an open source Vagrant configuration focused on WordPress development. Vagrant is a tool for building and managing virtual machine environments in a single workflow. These are recommended configurations for a system to match BC's production environment.

##Setup

####Set Up VVV
1. [**Install** the latest Virtualbox](https://www.virtualbox.org/wiki/Downloads). Make sure the latest VirtualBox is installed on your machine.
2. [**Install** the latest Vagrant](https://www.vagrantup.com/downloads.html) (v1.9.8 was used for this documentation).
3. **Install** the following Vagrant plugins with a terminal. *For users on a Windows 8+ machine, only the command prompt is properly supported*:
	1. Install the [vagrant-hostsupdater](https://github.com/cogitatio/vagrant-hostsupdater) plugin with `vagrant plugin install vagrant-hostsupdater`
	2. Install the [vagrant-triggers](https://github.com/emyl/vagrant-triggers) plugin with `vagrant plugin install vagrant-triggers`
4. **Clone** the Varying Vagrant Vagrants project into a local directory.
	1. `git clone -b master git://github.com/Varying-Vagrant-Vagrants/VVV.git vvv`
	2. This will clone the VVV project into a folder named 'vvv'.
5. In a terminal, change into the new directory with `cd vvv` and type `vagrant up` to start VVV.
	1. For Windows 8 or higher it is recommended that you run the cmd window as Administrator.
	2. The first run will take a while as your local machine downloads the required files.
	3. Your password may be required to move on in the installation process.

####Set Up vvv-custom.yml and Add a New Site
1. Go into the `vvv` folder using a file explorer.
2. Copy `vvv-config.yml`, paste it in place, and rename it as `vvv-custom.yml`
3. Open a text editor and uncomment the whole section starting with `#example site:` to be replaced with your site's information. Make sure to include the `wp-type'.
	* Before:
			example-site:
					repo: https://github.com/Varying-Vagrant-Vagrants/custom-site-template.git
					hosts:
						- my-example-site.dev
	* After:
				vvvmultisite:
                    repo: https://github.com/Varying-Vagrant-Vagrants/custom-site-template.git
                    hosts:
						- vvvmultisite.local
					custom:
 						wp_type: subdirectory
4. Run `vagrant reload --provision` to reload Vagrant, check provisions, and save your site.
5. Check to make sure http://vvv.dev/ works.
6. View your site at http://vvvmultisite.local/.
7. Visit the WP dashboard at http://vvvmultisite.local/wp-admin. Login with the standard wp-admin account settings `admin` and `password`.
8. Check at the top left that it allows multisites.

####If you can't connect to http://vvvmultisite.local/...
1. Make sure that vvv is listed under hosts in `C:\Windows\System32\drivers\etc\hosts`
2. Open the `hosts` file in a text editor.
		192.168.50.4 vvv.dev #Local Site
		192.168.50.4 vvv #Local Site
		192.168.50.4 local.wordpress.dev #Local Site
		192.168.50.4 vvvmultisite.local #Local Site
3. Run `vagrant reload --provision`

####Set Up Mapped Directories
1. Change into the `vvv` folder and create a new file called `Customfile` using a text editor. Make sure the 'C' is capitalized.
2. In the file, map your directories like so. Create a new line for each directory:
		config.vm.synced_folder "/Users/firstname.lastname/Projects/mayflower", "/srv/www/vvvmultisite/public_html/wp-content/themes/mayflower", :owner => "www-data", :mount_options => [ "dmode=775", "fmode=774" ]
3. Only change the firstname.lastname and the second link to map the directories as needed.
4. Run `vagrant reload --provision`

##Commands
Helpful commands for using VVV.
* `vagrant up` starts up Vagrant.
* `vagrant halt` powers off Vagrant.
* `vagrant ssh` accesses the server via the command line from your `vvv` directory.  You can do almost anything you would do with a standard Ubuntu installation on a full server.
* `vagrant provision` reapplies provisioning to a running box.
* `vagrant reload` reboots Vagrant.
* `vagrant reload --provision` runs reload and provision. Always use `vagrant reload --provision` when changes are made to any Vagrantfile, config or custom file.
* `vagrant destroy` destroys the Vagrant box. Any data stored in the virtual machine, including databases, will be deleted. Files added in the `www` directory will persist on the next `vagrant up`.

##Helpful Links
* [VVV Documentation](https://varyingvagrantvagrants.org/docs)
* [Install VVV](https://varyingvagrantvagrants.org/docs)
* [Adding a new VVV Site](https://varyingvagrantvagrants.org/docs/en-US/adding-a-new-site/)
* [Mapping plugin folder in VVV using shared folders](http://sudarmuthu.com/blog/mapping-plugin-folder-in-vvv-using-shared-folders/)

