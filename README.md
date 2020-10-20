# This is the guide to create git and github connection with a key
Download git
Configure details with the following two commands:
    git config --global user.name "INSERT YOUR GITHUB USERNAME HERE"
    git config --global user.email "INSERT YOUR GITHUB EMAIL ADDRESS HERE"
Create an SSH key pair using the following command in your git terminal:
    $ ssh-keygen -t rsa -b 4096 -C "THE SAME EMAIL ADDRESS AS BEFORE"
This will generate the key pairs. It will prompt you to "Enter a file in which to save the key", press Enter to use the default file location.
It will also prompt you to "Enter passphrase" and to repeat the passphrase, press Enter twice or repeat the desired passphrase.
Using the 'cd' command, go into the directory that the SSH key is saved in. When you are in the directory you should be able to list the files with the 'ls' command.
This should show two files, id(underscore)rsa which is your private key, and id(underscore)rsa.pub which is your public key.
Read from the public key using the 'cat' command:
    cat id_rsa.rb
Then copy this key by holding down the mouse in termux, selecting all of the text (from ssh-rsa all the way to the end of your email) and selecting copy from the dropdown menu.
Go to your GitHub account and click on the 'Settings' item in the profile menu in the top right of the screen. 
On the left hand side of the screen there should be a list starting with 'Profile'. Scroll down until you see the 'SSH and GPG keys' option and select it. 
There should be a green button labeled 'New SSH key'. Click this button. Create an appropriate name for the the key and paste the copied public key. Save the key and it should be set up!
