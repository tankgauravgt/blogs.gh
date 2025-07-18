---
title: "0026: Remove Duplicates from Sorted Array"
---
```python
class Solution:
    def removeDuplicates(self, nums):
        
        prev = None
        lx = 0
        for n in nums:
            if prev == n:
                continue
            prev = n
            nums[lx] = prev
            lx = lx + 1
        
        return lx
```
