
# Knowing your computer's name
- sfpc-x

# Command line
Walking inside of your computer

# SSH
Walk into other computers. We set up the Pis to have individual IP address and allow SSH. Secure Shell is a 'cryptographic network protocol for operating network services securely over an unsecured network.' 
 
## SSH into the teacher's computer

- ssh pi@sfpc-12 
- Are you sure you want to continue connecting (yes/no)? yes
- Password: morepoetry 
- All computers' passwords are the same 
- Now you are inside of the teacher's computer. Be mindful. 
- change directory to, cd folder-poetry
- cd mailbox 
- view the letter by cat letter.txt 
- Write a letter to the teachers by nano letter-from-mimi.txt or your name

## Set up your mailbox
- cd folder-poetry
- mkdir yourname-mailbox
- cd yourname-mailbox 
- such as mimi-mailbox 
  
### SSH into your neighbor's computer 
- ssh pi@sfpc-x 
- x is the number of your neighbor's computer. ask for consent. 
- navigate your neighbor's folders. Understand the folder structure. 
- Change Director to folder-poetry
- Send an 'electronic mail' by creating a file by 

```
nano letter.txt 

```

- Ctrl + O to save
- Ctrl + x to exit nano 
- To view the file, cat letter.txt 
- ctrl + d to get out of ssh 

# address
- /home/pi is the same as ~/

# Move files inside of your computer 

```
mv ~/Desktop/image.jpg ~/folder-poetry/mailbox 

```
# Send files to your friends mailbox

- scp stands for secure copy 
- download an image to your mailbox
- or, to move an existing image from the desktop, 

```
mv ~/Desktop/filename.jpg ~/folder-poetry/mimi-mailbox

```
- to send to a friend 

```
scp ~/folder-poetry/mimi-mailbox/image.jpg pi@sfpc-12:~/folder-poetry/mailbox/ 
```
From students A's Pi 'sfpc-1' to student B's Pi 'sfpc-2'
Student B would write this command to copy something from A's box into their box 

```
- scp pi@sfpc-1:~/folder-poetry/a-mailbox/letter.txt ~/folder-poetry/b-mailbox 

```
For student B to send a mail from their box to A's mailbox 


```
scp /home/pi/folder-poetry/b-mailbox/letter.txt pi@sfpc-1:/home/pi/folder-poetry/a-mailbox/

```
# dat share 
- dat share from folder-poetry 

```
dat share

```

- write an email to your friend with your dat hash 
- If you have a hash from your friend, cd to mailbox

```
dat clone hash

```
- you will clone your friend's folder poem and all of their emails