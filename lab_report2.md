# Lab Report 2
---
## Change#1

* Code difference
![](https://github.com/zhl010/CSE-15L/blob/5991486b493784a5153e27cc105bb487d0d19d8f/Commit%231.png)

* Failure inducing test file

    [test-file2.md](test-file2.md)

* Symptom
![](https://github.com/zhl010/CSE-15L/blob/5991486b493784a5153e27cc105bb487d0d19d8f/Symptom%231.png)

* Relation between the bug, the symptom, and the failure inducing input

After the first iteration of the while loop, a link was correctly added to the arraylist. Since there are extra texts after the link in test-file2, `currentIndex` is less than `markdown.length`, causing the while loop to keep on. 

In the second iteration, the method call `markdown.indexOf("[", currentIndex)` would return -1 since there are no more open brackets, therefore variable `nextOpenBracket` would be assigned value -1. 

Similarly for the next three method calls, the final consequence would be a `closeParen` with value -1. The `current index` would then equal 0. This led to a infinite while loop.

## Change#2

* Code difference
![](https://github.com/zhl010/CSE-15L/blob/5991486b493784a5153e27cc105bb487d0d19d8f/Commit%232.png)
 
* Failure inducing test file

    [test-file3.md](test-file3.md)

* Symptom
![](https://github.com/zhl010/CSE-15L/blob/5991486b493784a5153e27cc105bb487d0d19d8f/Symptom%232.png)

* Relation between the bug, the symptom, and the failure inducing input

In test-file3, there is an image in the format of `![link1](page.com)`. The current code in MarkdownParse.java only parse links by recognizing brackets and parenthesis, and would not check the exclamation mark which signifies an image. As a result, an image was wrongly parsed.

## Change#3

* Code difference
![](https://github.com/zhl010/CSE-15L/blob/5991486b493784a5153e27cc105bb487d0d19d8f/Commit%233.png)

* Failure inducing test file

    [test-file4.md](test-file4.md)

* Symptom
![](https://github.com/zhl010/CSE-15L/blob/5991486b493784a5153e27cc105bb487d0d19d8f/Symptom%233.png)

* Relation between the bug, the symptom, and the failure inducing input

In test-file4, there is a link after an image. The current code in MarkdownParse.java will `break` after recognizing an exclamation mark before the openbracket. In this case, the while loop ends before reaching the link because it met a `break` in first iteration dealing with the image. Thus, no links were parsed. 


[**Return to home page**](index.md)
