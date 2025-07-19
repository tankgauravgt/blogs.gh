---
title: "0003: Longest Substring Without Repeating Characters"
tags:
  - HashTable
  - String
  - SlidingWindow
---
```python
class Solution:
    def lengthOfLongestSubstring(self, s):
        
        lx = 0
        rec = {}
        
        cmax = 0
        for rx, c in enumerate(s):
            
            if c in rec and rec[c] >= lx:
                lx = rec[c] + 1
            
            rec[c] = rx
            cmax = max(cmax, rx - lx + 1)
        
        return cmax
```
