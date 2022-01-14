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

You should be prompted with a password like when you SSH'd earlier. Once you input it, you should be able to SSH back onto the server and use `ls` to see the `WhereAmI.java` file and even run it from the ieng6 computer using `javac` and `java`.

## Part 5: SSH Keys

So all this stuff is pretty cool but inputting your password everytime you want to SSH and do related things is annoying. Would be pretty cool if we had an autofill feature no?

SSH Keys. It's like a saved password using a program called `ssh-keygen` to create a public and private "key". The public key is put on the server, while the private stays on your client computer. 

Run key-gen like this: 

<img width="559" alt="Screen Shot 2022-01-14 at 11 34 20 AM" src="https://user-images.githubusercontent.com/97696585/149574670-9ac92d8f-c693-4a49-baff-12cbc76cb17c.png">

If you're on windows, follow these extra steps:

[https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation)

Then, we need to put the `id_rsa` file on the server using:
```
$ ssh cs15lwi22akh@ieng6.ucsd.edu
<Enter Password>
# now on server
$ mkdir .ssh
$ <logout>
# back on client
$ scp /Users/CharS/.ssh/id_rsa.pub cs15lwi22akh@ieng6.ucsd.edu:~/.ssh/authorized_keys
# You use your username and the path you saw in the command above
```

Now you can `ssh` or `scp` without inputting your password!

## Part 6: Making Remote Running Even More Pleasant 

There's a bunch of ways to perform commands or converting files between the client and server so try out what you've learned to try to figure them out!

Hints:
- If you put a command in quotes after you `ssh` it'll run on the remote server and then exit.

`$ ssh cs15lwi22zz@ieng6.ucsd.edu "ls"`

<img width="559" alt="Screen Shot 2022-01-14 at 11 44 17 AM" src="https://user-images.githubusercontent.com/97696585/149575793-fc02f042-1b5c-4e39-bbe6-624635f8d6bf.png">

- You can also use semicolons to run multiple commands

`$ scp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI`

-The up arrow also allows you to access past commands

## Conclusion

Basically, you've just hacked into the mainframe. 

`nice`