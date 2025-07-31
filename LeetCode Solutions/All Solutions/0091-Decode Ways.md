---
title: "0091: Decode Ways"
---
```python
class Solution:
    def numDecodings(self, s):
        
        i2c = {str(1 + ix): chr(ix + ord('A')) for ix in range(26)}
        
        @cache
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
