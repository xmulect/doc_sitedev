# Install WordPress

### Install Apache - Mysql - PHP

Check if the system default services is running:
```bash
  sudo service apache2 status
  sudo service mysql status
```
### Create the database for WordPress

#### Default system mysql

Enter mysql prompt:
```bash
  mysql -u root -p
```
type the password, then check the existed database in mysql prompt:
```
  SHOW DATABASES;
```
Build a mysql database for WordPress:
```
  CREATE DATABASE wpadmin;
```
Then:
```bash
  FLUSH PRIVILEGES;
```
#### With phpMyAdmin

Setup from Debian repository phpMyAdmin is easy:
```bash
  sudo apt-get install phpmyadmin
```
and include the web server settings in the configuration file: ``/etc/apache2/apache2.conf``:
```bash
  Include /etc/phpmyadmin/apache.conf
```
restart the web server, then open the link http://localhost/phpmyadmin/.

From 'Databases' card, enter new database name ``wpadmin``, press 'create'.

### Setup WordPress

Copy package to the directory `/var/www/`

Change owner:
```bash 
  sudo chown www-data:www-data -R wordpress/
```
Open url, http://localhost/wordpress/ to open setup page, press 'Let's go!', enter the database connection details:
```  
  database name: wpadmin
  mysql user: root
  password: ******
  database host: localhost
  table prefix: wp_
```
For privilege problem, the following warned:

>  Sorry, but I can’t write the ``wp-config.php`` file.
>
>  You can create the ``wp-config.php`` manually and paste the following text into it.

and manually copy the text in the frame to build ``wordpress/wp-config.php``.

Press 'Run the install', then comes the welcome page.



