# Deployment Plan
### Cortez_Toby_MDD_1409
---
1. **Set Up Github repo**
  1. Log-in to Github account
  
  2. Click Add New Repository
    1. Add a repo name
    2. initialize with a readme file
    
  3. Click Create Repository
	
2. **Set Up Server**
  1. SSH Into the Server as non root user
    
  2. Install Git
    1. sudo apt-get install git-core
      
	2. Configure Git
      1. git config --global user.name YOURNAME
	  2. git config --global user.email YOUR@EMAIL.COM
	  	
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
		  
  3. Create and change to the portfolio directory
  	1. mkdir portfolio
  	2. cd portfolio
  
  4. Initialize git
  	1. git init
  
  5. Pull files from Github
  	1. git pull origin master
  	
3. **Add files from local computer to server via ftp**
  1. add files to the portfolio directory to push to Github
  2. add files to /var/www so the portfolio is visible on the internet via server ip

4. **Back in terminal for the rest**
	1. view files ready to be staged
	  1. git status
	  
	2. Add files to the stage
		1. git add .
	
	3. Check to make sure all were added to the stage
		1. git status
	
	4. Make Commit
		1. git commit -m "Uploaded portfolio"
		
	5. Push to Github
		1. git push
		3. enter rsa password