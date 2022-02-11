# Lab Report 2 - Week 4 (1.28.22)

The past two weeks we worked on defining bugs vs symptoms and also learning how to better and more efficiently test code. 

This lab report will show some of the code changes we made and the reasoning behind the. 

## Code Change 1

![image](https://user-images.githubusercontent.com/97696585/151635622-92902435-6461-41f4-b13a-425005f98c88.png)

[Failure-Inducing Test File](https://github.com/Cubified/markdown-parse/blob/1df91be0281f16406aac62285e334d2a047984b2/breaking_test.md)

![image](https://user-images.githubusercontent.com/97696585/151636242-8f878cbd-e67f-4106-a786-ecccc4ba9060.png)

Our code had a bug where it would run on the assumption that the `nextOpenParenthesis` would be immediately after the `nextCloseBracket`. This caused a symptom of an `ArrayIndexOutOfBoundsException` when we inputted a file with a set of parenthesis far after the set of brackets. By adding a distance chek between the parenthesis and close bracket, we were able to fix this bug. 

## Code Change 2

![image](https://user-images.githubusercontent.com/97696585/151636627-033b3d19-9e44-47f4-8e80-2d6997b7af85.png)

[Failure- Inducing Test File](https://github.com/Cubified/markdown-parse/blob/6ba0ae2ede45ff4aba6fc5c04ced20fbb807fbfc/breaking_test_3.md)

![image](https://user-images.githubusercontent.com/97696585/151636921-19e9a46b-fbbb-4f8e-b772-2f716da34e86.png)

Our code had another bug where it would go into an infinite loop and have trouble assigning variables if given a file with and open parenthesis. Here, the symptom of the bug was a `StringIndexOutOfBoundsException` which we fixed by adding a conditional statemenet to exit said infinite loop when `nextOpenBracket == -1`.  

## Code Change 3

![image](https://user-images.githubusercontent.com/97696585/151637589-91fa34e7-76fc-49cb-8bba-6508adc0e709.png)

[Failure-Inducing Test File](https://github.com/sidnair01/markdown-parse/blob/8624b3128767922b0e65ccc5724bb4107ba01a69/test-file6.md)

![image](https://user-images.githubusercontent.com/97696585/151637742-a7e96e41-80c9-473b-b0c4-c65e25477780.png)

Another bug we had was that our code didn't check if a given link was part of an image. The symptom of this was that sometimes (like shown above) if our program was given an image, it would would spit out the link of the image as part of the returned array. To fix this we added a check that would see if `!` was before an openbracket, and thus the link was an image. 