---
title: "0300: Longest Increasing Subsequence"
---
```python
class Solution:
    def lengthOfLIS(self, nums):
        N = len(nums)
        
        # Maximum of below iterations:
        #     (sx + 1): [..., sx - 1] <sx> [sx + 1, ..., N - 1]
        #     (sx + 2): [..., sx - 1] <sx> [sx + 2, ..., N - 1]
        #     (sx + 3): .......................................
        # (sx + N - 1): [..., sx - 1] <sx> [sx + N, ..., N - 1]
        
        @cache
        def rec(sx):
            if sx == N:
                return 0
            cmax = 1
            for ix in range(sx + 1, N, 1):
                if nums[ix] > nums[sx]:
                    cmax = max(cmax, 1 + rec(ix))
            return cmax
        
        # Perform LIS starting from all indices:
        return max([rec(ix) for ix in range(N)])
```
