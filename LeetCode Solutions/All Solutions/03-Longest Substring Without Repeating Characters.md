---
title: "03: Longest Substring Without Repeating Characters"
tags:
  - HashTable
  - String
  - SlidingWindow
---
```python
class Solution:
    def lengthOfLongestSubstring(self, s):
        
        lx = 0
        rec = set()
        
        cmax = 0
        for rx, c in enumerate(s):
            if c not in rec:
                rec.add(c)
                cmax = max(cmax, rx - lx + 1)
            else:
                while s[lx] != c:
                    rec.remove(s[lx])
                    lx = lx + 1
                lx = lx + 1        
        return cmax
```