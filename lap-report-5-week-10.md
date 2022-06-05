## Lab Report 5

When finding the two tests I would use for this report I used the vimdiff command:
`vimdiff markdown-parser/results.txt new-markdown-parser/markdown-parser/results.txt`

link to test files where output differs:

# Test 1:

-[test1 201.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/201.md)

![test1](https://rwalsh299.github.io/cse15l-lab-reports/test1_201.png)

In this test my output is correct and the provided code gave the wrong output. There is no valid link in this file. The wrong implementation did not check for characters inbetween () and [] therefore it gave "baz" as the link. [CommonMark](https://spec.commonmark.org/dingus/), the output should be:

![test1](https://rwalsh299.github.io/cse15l-lab-reports/test1.png)

While Common Mark says it is a valid link, that is not what we are looking for as mention in the lab report. For the implimentation that is wrong, the issue is that it is not checking inbetween the () and [] for characters. 

![test2Error](https://rwalsh299.github.io/cse15l-lab-reports/test1Error.png)

To fix this inbetween these lines we should add a check for characters inbetween [] and ().

# Test 2:

-[test2 342.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/342.md)

![test2](https://rwalsh299.github.io/cse15l-lab-reports/test2_342.png)

In this test, my output is correct as there is no valid link in the file. While the provided code found the link to be "foo" and provides the wrong output.
According to [CommonMark](https://spec.commonmark.org/dingus/), the output should be:

![test2](https://rwalsh299.github.io/cse15l-lab-reports/test2.png)

For the implementation that is wrong, the back tics in the link is what is causing it to be in valid. The parser is not checking for back tics in the code, therefore it pulled the link in between the (). 

![test2Error](https://rwalsh299.github.io/cse15l-lab-reports/test2Error.png)

on line 75 it should be checking for back tix in the code.
