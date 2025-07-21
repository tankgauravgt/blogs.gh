---
title: "0139: Word Break"
---
```python
import functools

class Solution:
    def wordBreak(self, s, wordDict):
        max_wlen = max(map(len, wordDict))
        wset = set(wordDict)
        @functools.lru_cache(maxsize=None)
        def rec(s, sx):
            nonlocal wset
            if sx == len(s):
                return True
            if sx > len(s):
                return False
            flag = False
            for ix in range(1 + sx, sx + max_wlen + 1, 1):
                if s[sx:ix] in wset:
                    flag = flag or rec(s, ix)
            return flag
        return rec(s, 0)
```
