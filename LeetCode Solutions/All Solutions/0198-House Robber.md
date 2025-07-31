---
title: "0198: House Robber"
---
```python
from functools import lru_cache

class Solution:
    def rob(self, nums):
        
        @lru_cache(maxsize=None)
        def rec(sx):
            if ix >= len(nums):
                return 0
            takeit = nums[sx] + rec(sx + 2)
            skipit = rec(sx + 1)
            return max(takeit, skipit)
        
        return rec(0)
```
