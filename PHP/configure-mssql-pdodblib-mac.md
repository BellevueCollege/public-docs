# Configure PHP environment on Mac to connect to SQL Server using PDO interface #

_Valid for Mac OSX 10.10 (Yosemite) and probably OSX 10.9 (Mavericks) too._

PHP does not by default have tie-ins for SQL Server, so they must be compiled and included.  To connect to SQL Server using the PDO (PHP Data Objects) interface, you'll need to add MSSQL and PDO_DLIB extensions to PHP and enable them in `php.ini`.

Note: This documentation assumes you've already set up your PHP/Apache environment. For general PHP/Apache setup, refer to the PHP and Apache sections of [this setup guide](http://coolestguidesontheplanet.com/get-apache-mysql-php-phpmyadmin-working-osx-10-10-yosemite/).

## Before you start
1. Ensure you have the latest Xcode (or install it), and install the command line tools if you have not already done so. To install Xcode command line tools via the terminal:

		$ xcode-select ---install

2. Install Homebrew. 
Homebrew is a lovely package manager for Mac that makes installing and maintaining packages/utilities very easy. Visit the [Homebrew website](http://brew.sh) for the latest install instructions.

3. Install autoconf (package for generating configure scripts) using Homebrew.

		$ brew install autoconf

4. Install FreeTDS (libraries that allow Unix/Linux to talk to SQL Server) using Homebrew.

		$ brew install freetds
		
5. Download and extract PHP source.
Download the source code for the PHP version installed on your machine. This can be determined by using `php -v` from a terminal window. Once 
you know the version, download the correct tar.gz version from the [PHP releases webpage](http://php.net/releases). Then, from the directory of your PHP download, extract it.

		$ tar zxf php-5.5.14.tar.gz



## Build and add MSSQL extension

From the directory of your PHP download, you'll move to the MSSQL extensions folder, build the `mssql.so` file, then copy it to the PHP extensions folder.

	$ cd php-5.5.14/ext/mssql
	$ phpize
	$ ./configure --with-php-config=/usr/bin/php-config --with-mssql=/usr/local/
	$ make
	$ sudo cp modules/mssql.so /usr/lib/php/extensions/no-debug-non-zts-20121212

> **Note:** Your PHP extensions directory to copy the extension into may be different depending on your PHP version.

## Build and add PDO\_DBLIB extension

From the directory of your PHP download, you'll move to the PDO_DBLIB extensions folder of PHP, build the `pdo_dblib.so` file, then copy it to the PHP extensions folder.

	$ cd php-5.5.14/ext/pdo_dblib
	$ phpize
	$ ./configure --with-php-config=/usr/bin/php-config --with-pdo-dblib=/usr/local/
	$ make
	$ sudo cp modules/pdo_dblib.so /usr/lib/php/extensions/no-debug-non-zts-20121212

> **Note:** Your PHP extensions directory to copy the extension into may be different depending on your PHP version.

## Enable new modules and set MSSQL config variables in php.ini

The `php.ini` file is usually in `/etc` unless you have a non-standard install. If `php.ini` has not been used yet, you will see a file of `php.ini.default`. Copy that file to php.ini.

	$ cd /etc
	$ sudo cp php.ini.default php.ini

Open `php.ini` in the editor of your choice. To the bottom of the extensions section, add:

	extension=mssql.so
	extension=pdo_dblib.so

In the MSSQL section (around line 1600), change mssql.secure_connection to On.

	mssql.secure_connection = On

Restart Apache so the changes take effect.

	$ sudo /etc/apache2/apachectl restart

You can check that PHP is recognizing the new extensions using `phpinfo()`.


### Additional references that may be helpful

 * http://lkrms.org/php-with-freetds-on-os-x-mavericks/
 * http://blog.andyhunt.info/2013/11/29/php-mssql-pdo_dblib-freetds-support-on-mac-osx-10-9-mavericks/
 * http://php.net/manual/en/ref.pdo-dblib.php#94175