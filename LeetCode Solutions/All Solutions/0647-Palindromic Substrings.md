---
title: "0647: Palindromic Substrings"
---
```python
class Solution:
    def countSubstrings(self, s):
        N = len(s)
        count = 0
        # odd strings:
        for ix in range(N):
            lx = ix
            rx = ix
            while lx >= 0 and rx <= N - 1 and s[lx] == s[rx]:
                lx = lx - 1
                rx = rx + 1
                count = count + 1
        # even strings:
        for ix in range(N - 1):
            lx = ix
            rx = ix + 1
            while lx >= 0 and rx <= N - 1 and s[lx] == s[rx]:
                lx = lx - 1
                rx = rx + 1
                count = count + 1
        return count
```
