---
title: "0027: Remove Element"
---
```python
class Solution:
    def removeElement(self, nums, val):
        N = len(nums)
        
        write_head = 0
        for read_head in range(N):
            if nums[read_head] == val:
                continue
            nums[write_head] = nums[read_head]
            write_head = write_head + 1
            
        return write_head
```
