---
title: "0139: Word Break"
---
```python
class Solution:
    def wordBreak(self, s, wordDict):
        wdict = set(wordDict)
        w_max = len(max(*wdict, key=len))
        
        @cache
        def rec(sx):
            if sx >= len(s):
                return True
            flag = False
            for ws in range(1 + w_max):
                if s[sx:sx + ws] in wdict:
                    flag = flag or rec(sx + ws)
            return flag
        
        return rec(0)
```
