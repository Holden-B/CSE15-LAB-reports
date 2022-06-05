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
Test 14 resulted in `[/foo]` for our code and `[]` for the default code. While `/foo` is not a link, It does follow the correct Markdown link formatting. On the commonmark demo it shows as an underlined link that doesnt lead to anything, meaning that our code is more correct in this instance.

## Test 194

