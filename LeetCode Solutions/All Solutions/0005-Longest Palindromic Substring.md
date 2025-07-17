---
title: "0005: Longest Palindromic Substring"
---
```python
class Solution:
    def longestPalindrome(self, s):
    
        N = len(s)
        
        cmax = 0
        
        for ix in range(N):
            lx = ix
            rx = ix
            while lx >= 0 and rx <= N - 1 and s[lx] == s[rx]:
                lx = lx - 1
                rx = rx + 1
            if cmax < rx - lx - 1:
                cmax = rx - lx - 1
                rstr = s[lx + 1:rx]
                
        for ix in range(N - 1):
            lx = ix
            rx = ix + 1
            while lx >= 0 and rx <= N - 1 and s[lx] == s[rx]:
                lx = lx - 1
                rx = rx + 1
            if cmax < rx - lx - 1:
                cmax = rx - lx - 1
                rstr = s[lx + 1:rx]
                
        return rstr
```
