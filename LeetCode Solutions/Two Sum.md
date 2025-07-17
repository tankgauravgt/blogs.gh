---
title: "01: Two Sum"
tags:
  - Array
  - HashTable
---
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        rec = {}
        for ix, n in enumerate(nums):
            if n not in rec:
                rec[target - n] = ix
                continue
            return [ix, rec[n]]
        return [-1, -1]
```
