---
title: "0010: Regular Expression Matching"
---
```python
class Solution:
    def isMatch(self, s: str, p: str) -> bool:
        
        @cache
        def rec(sx, px):
            
            # if pattern ends, string must end too
            if px >= len(p):
                return sx == len(s)
            
            # check if prefix `can_match`:
            can_match = sx < len(s) and p[px] in {s[sx], '.'}
            
            # ---------------------------------
            # next_char == '*': 
            #     return `take_it` or `skip_it`
            # ---------------------------------
            if px < len(p) - 1 and p[px + 1] == '*':
                take_it = can_match and rec(sx + 1, px)
                skip_it = rec(sx, px + 2)
                return take_it or skip_it
            # ----------------
            # next_char != '*'
            # ----------------
            else:
                return can_match and rec(sx + 1, px + 1)
            
            return False
        
        return rec(0, 0)
```
