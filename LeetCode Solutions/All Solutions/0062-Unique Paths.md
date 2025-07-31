---
title: "0062: Unique Paths"
---
```python
class Solution:
    def uniquePaths(self, m, n):
	    
        @cache
        def rec(rx, cx):
            if rx == m - 1 and cx == n - 1: return 0
            if rx == m - 1: return 1
            if cx == n - 1: return 1
            count = 0
            count = count + rec(rx + 1, cx)
            count = count + rec(rx, cx + 1)
            return count
        
        return rec(0, 0)
```
