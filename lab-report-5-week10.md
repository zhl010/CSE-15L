# Lab Report 5
---
## How to find difference in test results

I used commandline: 

`bash script.sh > XXX.txt` 

to store test results of both my implementation and provided implementation. Then, I used: 

`diff XXX1.txt XXX2.txt > Diff.txt`

to compare the two result txt files and store the comparison output.

I will pick two tests from the tests for which Diff.txt showed a difference with different implementation of markdown `getLink()` method.

## Test One

Here are part of the Diff.txt:

```
212c212
< [url]
---
> []
```

By looking at the bash result files, we found that line 212 corresponds to test file `194.md`.

Here is the link to test markdown file `194.md`:
[194.md]()



[**Return to home page**](index.md)