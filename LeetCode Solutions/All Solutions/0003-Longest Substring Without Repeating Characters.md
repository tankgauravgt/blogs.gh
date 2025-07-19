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
        cmax = 0
        
        cache = {}
        for rx, c in enumerate(s):
	        
			# only look in current window:
            if c in cache and cache[c] >= lx:
                lx = cache[c] + 1
            
            cache[c] = rx
            cmax = max(cmax, rx - lx + 1)
        
        return cmax
```
