---
title: "0128: Longest Consecutive Sequence"
---
```python
class Solution:
    def longestConsecutive(self, nums):
        rec = set(nums)
        cmax = 0
        for n in nums:
            if n - 1 in rec:
                continue
            temp = 1
            while n + 1 in rec:
                temp = temp + 1
                n = n + 1
            cmax = max(cmax, temp)
        return cmax
```
