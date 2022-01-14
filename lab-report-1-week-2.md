# Lab Report 1 - Week 2 (1.9.22)
So what the hell is this SSH thing? Honestly I'm still not totally sure but I know it stand for "Secure Shell" and it lets someone connect to a server and do a buncha cool stuff. 

**How does one do it?**

## Step 1: Visual Studio Code

A quick google search will find you the download link for VSCode. Then, you can open a window that looks something like this:

!<img width="450" alt="Screen Shot 2022-01-14 at 12 06 41 AM" src="https://user-images.githubusercontent.com/97696585/149473822-aef353cb-d47d-4913-b0fd-0b6f78b68dd1.png">

## Step 2: Remotely Connecting 
*(The hard step in my opinion)*

We begin with downloading OpenSSH (only if you're on windows otherwise you can skip this step), a program that lets computers connect to other computers with this type of account. 

[Install OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)

Then, using your course-specific account here:

[UCSD Account Lookup](https://sdacs.ucsd.edu/~icc/index.php)

We can open a terminal in VSCode (Ctrl or Command + `) and perform this command (with "zzz" replaced with your account specific code):

`$ ssh cs15lwi22zzz@ieng6.ucsd.edu`

Some message will pop up - you can just say yes. Then, a password prompt will pull up (if you have any issues with password resetting take a look on piazza or ask!) and after you input it, your screen should look something like this:

<img width="450" alt="Screen Shot 2022-01-14 at 12 37 39 AM" src="https://user-images.githubusercontent.com/97696585/149480941-816f6d06-f647-4b9d-bedf-4504d4090512.png">

## Step 3: Run Some Commands!
*(The fun part)*

Try these commands! They might perform differently based on if you're on Windows or OSX (Most commands run on a client terminal in VSCode will still work for the computer youre SSh'd to!!).

```
Commmands:
cd ~
cd
ls -lat
ls -a
ls <directory> 
cp /home/linux/ieng6/cs15lwi22/public/hello.txt ~/
cat /home/linux/ieng6/cs15lwi22/public/hello.txt
```
For Example: 

<img width="650" alt="Screen Shot 2022-01-14 at 12 51 23 AM" src="https://user-images.githubusercontent.com/97696585/149486620-4b166317-50c9-44e7-8be3-c67e9c38b98e.png">

## Step 4: Moving Files Over SSH With SCP 
*(The cool part)*

This step is awesome because I was in New York when I first copied files between my computer and the server in UCSD. 

You'll wanna create a file called `WhereAmI.java` with the following contents:

<img width="715" alt="Screen Shot 2022-01-14 at 12 57 58 AM" src="https://user-images.githubusercontent.com/97696585/149487637-efea1a9e-6491-49ae-9905-38b0be95d169.png">

On your computer (NOT while SSH'd into the server) run the file using `javac` and `java`. Then, in the terminal, run:

`scp WhereAmI.java cs15lwi22zzz@ieng6.ucsd.edu:~/`