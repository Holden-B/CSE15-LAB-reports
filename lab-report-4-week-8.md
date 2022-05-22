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

