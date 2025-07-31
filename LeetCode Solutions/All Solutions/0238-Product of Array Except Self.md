---
title: "0238: Product of Array Except Self"
---
```python
class Solution:
    def productExceptSelf(self, nums):
        N = len(nums)
        res = [1] * N
        prod = 1
        for ix in range(0, N, 1):
            res[ix] *= prod
            prod *= nums[ix]
        prod = 1
        for ix in range(N - 1, -1, -1):
            res[ix] *= prod
            prod *= nums[ix]
        return res
```
