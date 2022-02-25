# Lab Report 4 - Week 8 (2.25.21)

For this week's lab, we're testing some differences between two MarkdownParse implemenations, and seeing how they both perform on the same set of 3 complex files. 

We will comparing my implementation [here](https://github.com/charles-lau2021/markdown-parse-self.git) with the reviewed implementation [here](https://github.com/yi113/markdown-parse).

<img width="666" alt="Screen Shot 2022-02-25 at 9 36 13 AM" src="https://user-images.githubusercontent.com/97696585/155733367-a0a6e3c0-32eb-4f9d-9775-3b097b5ac3c4.png">

These are the tests that will be used, which are added to both implementations of MarkdownParse. (Based off of VSCode preview)

## Output for My Implementation
<img width="1028" alt="Screen Shot 2022-02-25 at 9 37 16 AM" src="https://user-images.githubusercontent.com/97696585/155733567-27c6da6f-dd82-4c22-87e8-326b038adcf9.png">


Here we see that all 3 tests failed.

## Output for Reviewed Implementation
<img width="1028" alt="Screen Shot 2022-02-25 at 9 38 46 AM" src="https://user-images.githubusercontent.com/97696585/155733833-b951192c-ead3-4c67-a24c-36b79826efbd.png">

Here we see that all 3 tests failed again.

## Potential Fixes

1. Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.

    Answer: Yes. We could implement a check that if there is an "open" backtick, to look for the index of a 'close" backtick. And if it finds the "close" one, it could update currentIndex to the index of the "close" backtick + 1 which would effectively ignore any text inbetween the backticks. 
2. Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets? If yes, describe the code change. If not, describe why it would be a more involved change.

    Answer: No. For the snippet 2 test, we could implementing a check that will determine if there is a nested bracket or such. For example, for nested brackets, it would just see if there is are anymore close brackets before the next openParenthesis, and then use the index of the farthest closeBracket as the value for closeBracket, effectively ignoring the close brackets in the middle. To implement this for nested parentheses, brackets, and escaped brackets would probably require more than 10 lines of code.
3. Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? If yes, describe the code change. If not, describe why it would be a more involved change.

    Answer: Yes. To fix the snippet 3 test, I think one could implement a check for `"\n"` within the string between the parenthesis and simply move the currentIndex past the end of the new line which would basically ignore the new line. I this could be done easily under 10 lines. 