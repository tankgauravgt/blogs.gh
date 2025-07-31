---
title: "0125: Valid Palindrome"
---
```python
class Solution:
    def isPalindrome(self, s):
        s = s.lower()
        s = list(filter(lambda x: x.isalnum(), list(s)))
        return s == s[::-1]
```
