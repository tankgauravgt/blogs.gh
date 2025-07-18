---
title: "0010: Regular Expression Matching"
---
```python
class Solution:
    def isMatch(self, s1, p1):
        @cache
        def rec(s, p, sx, px):
            
            if px == len(p): 
                return sx == len(s)
                
            fmatch = (sx < len(s)) and (s[sx] == p[px] or p[px] == '.')
            if px < len(p) - 1 and p[px + 1] == '*':
	            flag1 = rec(s, p, sx, 2 + px)
	            flag2 = fmatch and rec(s, p, 1 + sx, px)
	            return flag1 or flag2
            else:
                return fmatch and rec(s, p, 1 + sx, 1 + px)
        
        return rec(s1, p1, 0, 0)
```
