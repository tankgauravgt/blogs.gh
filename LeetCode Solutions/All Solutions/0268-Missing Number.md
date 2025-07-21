---
title: "0268: Missing Number"
---
```python
class Solution:
    def missingNumber(self, nums):
        s = 0
        for n in nums:
            s += n
        N = len(nums)
        return ((N * (N + 1)) // 2) - s
```
