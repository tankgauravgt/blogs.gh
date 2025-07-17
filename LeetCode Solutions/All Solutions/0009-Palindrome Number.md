---
title: "0009: Palindrome Number"
---
```python
class Solution:
    def isPalindrome(self, x):
        return str(x) == str(x)[::-1]
```
