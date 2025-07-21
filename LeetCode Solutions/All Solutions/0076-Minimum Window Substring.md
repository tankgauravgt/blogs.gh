---
title: "0076: Minimum Window Substring"
---
```python
from collections import Counter

class Solution:
    def minWindow(self, s, t):
        
        tgt = Counter(t)
        
        lx = 0
        src = {}
        cmin = 1e9
        out = ""
        for rx, c in enumerate(s):
            
            src[c] = src.get(c, 0) + 1
            
            while all([src.get(cc, 0) >= tgt[cc] for cc in t]):
                if cmin > rx - lx + 1:
                    cmin = rx - lx + 1
                    out = s[lx:rx + 1]
                src[s[lx]] -= 1
                lx = lx + 1
        
        return out
```