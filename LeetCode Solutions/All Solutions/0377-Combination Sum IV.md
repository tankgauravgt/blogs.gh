---
title: "0377: Combination Sum IV"
---
```python
from functools import lru_cache

class Solution:
    def combinationSum4(self, nums, target):
        nums.sort()
        @lru_cache(maxsize=None)
        def rec(rem):
            if rem < 0:
                return 0
            if rem == 0:
                return 1
            count = 0
            for n in nums:
                if rem < n: break
                count = count + rec(rem - n)
            return count
        return rec(target)
```
