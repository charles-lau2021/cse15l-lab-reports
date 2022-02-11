# Lab Report 3 - Week 6 (2.11.21)

Hello! The last couple of weeks in lab we've just been using all sorts of different methods that make it easier to either run programs or access different things such as `bash scripts` or `streamlining ssh configs`. 

This lab report will show how we can copy whole directories with `scp -r`. 

`scp -r . cs15lwi22akh@ieng6.ucsd.edu:~\lab-6`

By using `-r` after `scp`, it tells the command to run recursively, allowing us to copy a folder and all its contents. `.` specifies the source, or the current directory, while the `~/lab-6` tells `scp` which directory to copy.

![image](https://user-images.githubusercontent.com/97696585/153660241-0dea59ff-e673-4420-9a0e-f89c26708b03.png)

![image](https://user-images.githubusercontent.com/97696585/153661222-7910f7d3-7b8f-47e0-b38c-aac90e85f472.png)

If we look here, using `ls` we can see that my directory `lab-6` succesfully copied over. 

In lab 6, we created a `makefile` that can make running tests easier. This file can be run on the `ssh` server now that I copied the directory it's in over. 

![image](https://user-images.githubusercontent.com/97696585/153661670-19556d01-42f4-4838-ab44-7be496ee5cd9.png)

Like in the first lab report, multiple commands can also be run at one time using `;` (although froom my tests it seems like windows is limited to 2 maximum commands on one line). 

![image](https://user-images.githubusercontent.com/97696585/153662702-dc7dac80-55ab-4a39-b9f8-377d30702e8d.png)

Here, I'm using `scp` and `ssh` in one line. 

![image](https://user-images.githubusercontent.com/97696585/153662834-60bf92c1-d416-46df-9ac0-78af506ef3f4.png)

And here, I'm using `cd` and `make test` in one line. 