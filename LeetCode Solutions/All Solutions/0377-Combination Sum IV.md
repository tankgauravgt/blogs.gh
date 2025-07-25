---
title: "0377: Combination Sum IV"
---
```python
from functools import lru_cache

class Solution:
    def combinationSum4(self, nums, target):        
        @lru_cache(maxsize=None)
        def rec(curr, tgt):
            if curr >= tgt:
                return int(curr == tgt)
            total = 0
            for n in nums:
                total = total + rec(curr + n, tgt)
            return total
        return rec(0, target)
```
