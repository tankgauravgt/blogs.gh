---
title: "0198: House Robber"
---
```python
from functools import lru_cache

class Solution:
    def rob(self, nums):
        cmax = 0
        @lru_cache(maxsize=None)
        def rec(ix, last, curr):
            nonlocal nums, cmax
            if ix >= len(nums):
                cmax = max(cmax, curr)
                return curr
            if last != True:
                rec(1 + ix, True, curr + nums[ix])
            rec(1 + ix, False, curr)
        rec(0, False, 0)
        return cmax
```
