# Lab Report 2
> For this lab report, we were tasked with debugging a link parser that takes markdown files as input and outputs a list of web addresses.

**Our changes aimed to fix the following problems:** 
- Reject image links
- Link at the start of file
- Reject links with spaces

## Rejecting image links
> Images in Markdown are very similar in format to links, this caused image addresses to be saved in the output list. There is one key difference though, image format starts with an exclamation point (!). In the initial code, the symptom of this was image links being copied into the list, caused by the bug of lack of conditional statement checking for the image format.
> 
> To solve this, we added a conditional statement that ensured there was not an exclamation point before the Open bracket. (lines 19-21)
> 
> [Failure Inducing Input](https://github.com/Holden-B/markdown-parser/blob/main/test-file2.md)

**Our Changes:**
![image](https://user-images.githubusercontent.com/103291577/165006179-62e46fbe-a82c-40fe-a602-3231357a3673.png)

**Symptom:**
![image](https://user-images.githubusercontent.com/103291577/165013115-259f2efb-9402-4136-a398-91651d8062d7.png)

## No parenthesis or brackets, or both
> Having no brackets or parenthesis created a failure inducing input. This was due to the `indexOf()` method. The symptom here is that indexOf returns -1 if there is none of the desired character(s) within the String. Because MarkdownParse uses values that are gotten with `indexOf` as an indexing variable, it creates an `IndexOutOfBoundsException`. To solve this, we added a conditional statement that would break the loop if any of the `indexOf()` variables were equal to -1. 

**Our Changes:**
![image](https://user-images.githubusercontent.com/103291577/165009151-3ae46cf7-6e3f-4abf-82ff-2e999e989715.png)

**Symptom:**
![image](https://user-images.githubusercontent.com/103291577/165011286-087a8913-f3d3-4fdd-b09a-82dfa4711db5.png)

## Rejecting links with spaces
> Another issue we encoutered that didnt necessarily break the program, but instead just took unusable bad input. The program would take links that had spaces in them. This is an issue as these "links" would not work, leading to a symptom of improper data collection. To fix this bug, we created another conditional statement that would check if there was any space character within the parenthesis and continue past while iterating the while loop conditional.

**Our Changes:**
![image](https://user-images.githubusercontent.com/103291577/165011682-05bbd3c1-a41e-468e-b126-52f794c1c9f0.png)

**Symptom:**
![image](https://user-images.githubusercontent.com/103291577/165012631-00726877-f937-44c6-b488-291fdcf03072.png)







