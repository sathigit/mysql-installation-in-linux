 Welcome to mysql installation in linux
 How to Install and Use MySQL on Ubuntu 16.04


Install MySQL
1.We can install MySQL by using the apt package manager. First make sure your packages list are up to date. Open the terminal and run this apt command.

	$ sudo apt-get update




2.We need to install the mysql-server package, which downloads the required files, configures the initial database set up and handles running MySQL as a system service. Run this apt command to get the process started.

	$ sudo apt-get install mysql

An administrative screen asking for a new root password will appear in the middle of the package installation process. Enter your chosen new password twice and the installation will continue.





3.Creating MySQL Users

To create a non-root user, connect to the MySQL instance with the mysql command line client.
 
 	$ mysql -u root -p



It will ask for password (root password that you entered when installing)

4.Now use the CREATE USER command to generate a new user. Make sure to change "userName" and "userPassword" with your own values.

	$ CREATE USER 'userName'@'localhost' IDENTIFIED BY 		   'userPassword';


No output after the command is good - that means the command succeeded.

5.We need to apply privileges to the new user so it can handle basic database operations. Again, make sure to replace the default username in this command with your new username.

	$ GRANT ALL PRIVILEGES ON * . * TO 'userName1'@'localhost';



6.It's a good idea to reload the privileges to make sure our new user's permissions are in place.

	$ FLUSH PRIVILEGES;


New User Connection

7.We're set to connect to the database with our new user. Exit the MySQL client with "Ctrl-d". Reconnect using a slightly different command than we used earlier.

	$ mysql -u mynewuser -p

8.Create a new database with the CREATE DATABASE command.

	$ CREATE DATABASE amazon;

9.Connect to the new database with the USE command.

	$ use amazon;

10.Create a simple new table with the CREATE TABLE command.

	$ CREATE TABLE pages (name VARCHAR(50), url VARCHAR(100));









