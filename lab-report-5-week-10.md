# Lab Report 5 - Week 10 (3.11.22)
Final week!

Today we are comparing two implementations, my own and the one fom lab 9, and
against the 652 commonmark-spec tests. 

First, I copied both repositories to the ieng6 server, then opened each implementation in a seperate terminal. I edited (using `vim`) the bash script 
of each file to include an `echo $file` command after each output. Then, I ran
both using `make` then `bash script.sh` and copied the two different outputs to 
their own text file. After using `ctrl + f`, I simply found two cases with 
different outputs. 

*(The first picture will show the lab 9 implementation, and the second shows mine)*

## Bug 1

![image](https://user-images.githubusercontent.com/97696585/157980831-0fb7f8e9-47b1-4958-a37d-dcbc87bd9a84.png)

![image](https://user-images.githubusercontent.com/97696585/157980911-9acb0fdf-f59e-4ecb-aaf3-c40c98055dbc.png)

As shown here, 

![image](https://user-images.githubusercontent.com/97696585/157981308-95cc05d5-fe31-4697-8d93-5c960a525492.png)

it seems like my implementation is incorrect. According to the VSCode preview, the link format is not correct and thus shouldn't be outputted. The bug in my code is that my program will simply believe that any text between the two parenthesis is a link, meaning there needs to be a check for perhaps `.com`, `.org`, or etc at the end of the supposed link.  

![image](https://user-images.githubusercontent.com/97696585/157982609-c6660517-064e-4e68-98e3-01541174b32a.png)

Here, we see there is no check for the text in between the parenthesis. 

## Bug 2

![image](https://user-images.githubusercontent.com/97696585/157983042-0bfd746e-43fc-444b-9454-21d29e94015b.png)

![image](https://user-images.githubusercontent.com/97696585/157983107-482acb64-4268-4ae2-9c0f-ca5b15165c99.png)

As shown here, 
![image](https://user-images.githubusercontent.com/97696585/157983265-dc7f3709-755f-46da-bdc5-549dd0a1b0ad.png)

it seem that my implementation is correct. According to the VSCode preview, the "link" that the lab 9 implementation prints out is actually the link to an image and thus shouldn't be outputed. The bug is that the lab 9 implementation does not have a check for `!` in front of each open bracket. 

And we can see that here 

![image](https://user-images.githubusercontent.com/97696585/157983762-15e98928-8bd7-4b52-9407-ae142df326e2.png)