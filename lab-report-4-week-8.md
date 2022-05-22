# [Lab Report 4](https://docs.google.com/document/d/1q7HzkBHREFiAFCbs5-SdMA8vxfdkV2vxAqGMB-haE5U/edit)
### In this lab we will look at some more edge cases for `MarkdownParse`
We will look at these new test cases and how our group and the group we reviewed's `MarkdownParseTest` code handle.

> Snippet 1
> 
> Snippet 2
> 
> Snippet 3

#### [Our groups `MarkdownParse` repository](https://github.com/Holden-B/markdown-parser)

#### [MarkdownParse repository we reviewed](https://github.com/leahkuruvila/markdown-parser)



## Snippet 1:

Snippet one features 4 total links but the 2nd and 4th ones are broken and shouldnt be taken as input. The expected ArrayList output should be: 

`['google.com, google.com, ucsd.edu]`

In my test case, I checked that the size of the list was 3 and the first element of the arrayList was `'google.com`

**This is the result for the code we reviewed:**

![image](https://user-images.githubusercontent.com/103291577/169720335-71ff0547-b481-43ec-964f-48d30f50a9c1.png)

This code got the correct amount of links, but the wrong ones. It got the first `url.com` link, although according to CommonMark, it is incorrect.

### Resolution:
The issue here is the use of backticks in Markdown. This code doesnt have any conditions that checks the use of backticks. This would be fairly easy to implement. You would need to check if there is an opening and closing backtick and if any brackets or parenthesis are contained within, invalidating the link and continuing with the file.

## Snippet 2:

Snippet 2 features nested parenthesis and brackets. The actual link ouput should look as follows:

`[a.com, a.com(()), example.com]`

In my test case, I did something similar to the first one. I checked the size was correct and the first link is equal.

**This is the result for the code we reviewed:**

![image](https://user-images.githubusercontent.com/103291577/169720759-f8a509a8-5ac5-47a4-b0f7-4ee426a98c3b.png)

This code semi passed the vibe check. it got the first URL correct, the nested one. It didnt get the size correct. The URL recorded `a.com(())` as `a.com((`.

### Resolution:
The issue with this code is that it doesnt count the amount of parenthesis or match them, meaning that when it sees the first `)` in `a.com(())` it stops and takes that as a link. This could be solved with a stack data structure to ensure bracket, parenthesis, and other symbol completeness. It would likely be its own method or longer than 10 lines.


## Snippet 3:

Snippet 3 features lots of broken lines and only one of them technically counts as a link. The output should be as expected:

`[https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]`
