# Lab Report 5

> In this lab report we will be looking at the multitude of `markdown-parser` test files from lab 9
>
**Specifically we will look at:**
- Finding different test results
- comparing outputs with `CommonMark`
- describing what failed within the program


## Finding tests with different results
Due to the large amount of test files, using `vimdiff` was the most efficient way to observe differences between two implementations.

![SharedScreenshot](https://user-images.githubusercontent.com/103291577/172047116-3cdea2ff-bada-4d16-9f37-ca423f327cd3.jpg)

### Within this report we will look at Files:

>[test-14](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/14.md)
>
>[test-194](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/194.md)

## Test 14
Test 14 resulted in `[/foo]` for our code and `[]` for the default code. While `/foo` is not a link, It does follow the correct Markdown link formatting. On the commonmark demo it shows as an underlined link that doesnt lead to anything. The default code is correct in this instance.

## Test 194
Test 194 resulted in `[url]` in our code and `[]` in the default code. This test is similar to the last one, it is not a link but is posed to look like a link. This one should not work as there is no real link and there is characters in between the end bracket and parenthesis.

![image](https://user-images.githubusercontent.com/103291577/172048686-b26d2a3d-f624-434a-9bab-22f88f8e15dd.png)

## Test 14 bug
The problem for test 14 could be approached in a couple of different ways. The markdown formatting is correct, although there is no characters that would indicate what is enclosed in the parenthesis is actually a link. This could be solved in a couple of ways. I would say that having some sort of check that ensures there is a domain string (ex .com, .org, etc.). This wont ensure correctness always though such as `url.com` isnt a real URL. This doesnt facilitate an issue with the current code, but instead something to be added additionally. 
