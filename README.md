# This is the guide to create a git and github connection with a key on ChromeOS
## Setting up git
- Download termux from the App Store
- Open termux and use the following command to download git to your machine

```apt install git```

- If other packages are required at this or any further stage, simply follow the instructions in the termux terminal to install the necessary packages
- Once this is complete, type the following command to check the that git has properly installed. The result should be git followed by a number

```git --version```
- Now that git is correctly installed, we neeed to configure details with the following two commands:

```git config --global user.name "INSERT YOUR GITHUB USERNAME HERE"```

```git config --global user.email "INSERT YOUR GITHUB EMAIL ADDRESS HERE"```
## Creating your key pairs
- Create an SSH key pair using the following command in your git terminal:

```$ ssh-keygen -t rsa -b 4096 -C "THE SAME EMAIL ADDRESS AS BEFORE"```
- This will generate the key pairs. It will prompt you to "Enter a file in which to save the key", press Enter to use the default file location.
- It will also prompt you to "Enter passphrase" and to repeat the passphrase, press Enter twice or repeat the desired passphrase.
- Using the 'cd' command, go into the directory that the SSH key is saved in. When you are in the directory you should be able to list the files with the 'ls' command.
- This should show two files, id(underscore)rsa which is your private key, and id(underscore)rsa.pub which is your public key.
- Read from the public key using the 'cat' command:

```cat id_rsa.rb```
- Then copy this key by holding down the mouse in termux, selecting all of the text (from ssh-rsa all the way to the end of your email) and selecting copy from the dropdown menu.
- Go to your GitHub account and click on the 'Settings' item in the profile menu in the top right of the screen. 
- On the left hand side of the screen there should be a list starting with 'Profile'. Scroll down until you see the 'SSH and GPG keys' option and select it. 
- There should be a green button labeled 'New SSH key'. Click this button. Create an appropriate name for the the key and paste the copied public key. Save the key and it should be set up!

## Committing and pushing to github
- Create a new repository with the 'git init' command:

```git init```

- Create a file using 'touch' command. Below is a command to make a standard read me file in md format:

```touch README.md```

- Now there is a file on your localhost (your laptop/PC) that is not present in your GitHub repository. Let's change that. Use the 'git add' command to prepare files for the next commit:

```git add .```

- The full stop makes it so that all new files and folders in the current filepath are added to the index. You may also specify a specific filename in place of the '.'
- At this stage you may use the 'git status' command to see the queued files:

```git status```

- Now we can try to commit the files using the 'git commit' command:

```git commit -m "This is a useful message about what changes you've made"````
- Now we will rename the current branch with the 'git branch' command:

```git branch -M main```
- Now we need to add the remote repository that our local repository will connect to before pushing the commits:

```git remote add origin git@github.com:jatkin-wasti/Engineering_74_business_week.git```
- And finally, we can now push these changes to the cloud with the 'git push' command:

```git push -u origin main```
- Congratulations! You successfully set up git and github, and even did your first commit!
- In the future, if you would like to commit more changes, you only need to do the following steps:

```git add .```

```git commit -m "Insert useful message here"```

```git push origin main```
- Adding text to see if this clone worked correctly
