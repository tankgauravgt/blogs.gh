---
title: "0091: Decode Ways"
---
```python
from functools import lru_cache

class Solution:
    def numDecodings(self, s):
        i2c = {str(1 + ix): chr(ix + ord('A')) for ix in range(26)}
        @lru_cache(maxsize=None)
        def rec(ix):
            if ix == len(s):
                return 1
            count = 0
            for k, v in i2c.items():
                if s[ix::].startswith(k):
                    count = count + rec(ix + len(k))
            return count
        return rec(0)
```
