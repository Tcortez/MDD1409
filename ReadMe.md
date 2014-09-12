# Deployment Plan
### Cortez_Toby_MDD_1409
---
1. **Set Up Server**
---
  1. SSH Into the Server
    1. ssh root@Server_IP_Address
    2. Enter password
---
  2. Create Non-Root User
    1. adduser Username
    2. adduser Username
  3. End SSH Session
    1. exit
  4. Login as Non-Root User
    1. ssh Username@Server_IP_Address
    2. Enter password
  5. Update Package System
    1. sudo apt-get update
    2. Enter password
  6. Upgrade Package System
    1. sudo apt-get upgrade
  7. Update Packages for Newly Installed Version
    1. sudo apt-get update
  8. Update System level Packages
    1. sudo aptitude update
    2. sudo aptitude safe-upgrade
    3. sudo reboot
  9. Install Packages
    1. Install Git
      1. sudo apt-get install git-core
	  2. Configure Git
      	1. git config --global user.name “NAME”
	  	2. git config --global user.email Your@Email.com
	  3. Confirm Settings
      	1. git config --list
	  4. Create SSH Keys for Github Access
      	1. ssh-keygen -t rsa -C ”YourEmail@example.com”
        	*_This will ask if you want to customize the name, you don’t. Just press enter._
		2. Enter a passphrase
		3. Re-enter the passphrase
	  5. Put the RSA key on file with github.com so this server is treated as a trusted machine.
      	1. less ~/.ssh/id_rsa.pub
	  	2. Copy ALL of the contents of this file to your clipboard.
	  	3. Add new SSH Key to your Github account under the Account Settings.
        	1. Click the Add Key button
			2. Enter a title defining the server
			3. Paste the RSA file’s contents into text area marked “Key”
			4. Click Add Key
    2. Install Apache 2
      1. sudo apt-get install apache2
      2. Configure ServerName
      3. Restart Server
        1. sudo service apache2 restart
      4. Restrict Access
        1. sudo pico /etc/apache2/conf.d/security
        2. Uncomment <Directory />
        3. Add Options FollowSymLinks
      5. sudo service apache2 restart
      6. Change Permissions to Allow Access
      7. sudo chown -R UserName /var/www
