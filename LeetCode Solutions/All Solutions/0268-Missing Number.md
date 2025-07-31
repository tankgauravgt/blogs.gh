---
title: "0268: Missing Number"
---
```python
class Solution:
    def missingNumber(self, nums):
        N = len(nums)
        return ((N * (N + 1)) // 2) - sum(nums)
```
