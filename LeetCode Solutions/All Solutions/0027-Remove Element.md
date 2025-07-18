---
title: "0027: Remove Element"
---
```python
class Solution:
    def removeElement(self, nums, val):
        
        lx = 0
        for ix, n in enumerate(nums):
            if n == val:
                continue
            nums[lx] = n
            lx = lx + 1
        
        return lx
```
