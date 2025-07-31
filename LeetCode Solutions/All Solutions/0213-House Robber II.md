---
title: "0213: House Robber II"
---
```python
class Solution:
    def rob(self, nums):
        N = len(nums)
        
        @cache
        def rec(sx, ex):
            if sx >= ex:
                return 0
            takeit = nums[sx] + rec(sx + 2, ex)
            skipit = rec(sx + 1, ex)
            return max(takeit, skipit)
        
        return max(rec(0, N - 1), rec(1, N)) if N > 1 else nums[0]
```
