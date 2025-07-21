---
title: "0213: House Robber II"
---
```python
from functools import lru_cache

class Solution:
    def rob(self, nums):
        @lru_cache(maxsize=None)
        def rec(ix, lim, last=False):
            if ix == lim:
                return 0
            total = 0
            if not last:
                total = max(total, nums[ix] + rec(1 + ix, lim, last=True))
            total = max(total, rec(1 + ix, lim, last=False))
            return total
        N = len(nums)
        return max(rec(0, N - 1, False), rec(1, N, False))
```
