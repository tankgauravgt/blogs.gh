---
title: "0300: Longest Increasing Subsequence"
---
```python
from functools import lru_cache

class Solution:
    def lengthOfLIS(self, nums):
        @lru_cache(maxsize=None)
        def rec(ix, prev):
            if ix == len(nums):
                return 0
            cmax = float('-inf')
            if nums[ix] > prev:
                cmax = max(cmax, 1 + rec(1 + ix, nums[ix]))
            cmax = max(cmax, rec(1 + ix, prev))
            return cmax
        return rec(0, float('-inf'))
```
