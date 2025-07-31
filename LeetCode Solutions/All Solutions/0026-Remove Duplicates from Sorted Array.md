---
title: "0026: Remove Duplicates from Sorted Array"
---
```python
class Solution:
    def removeDuplicates(self, nums):
        N = len(nums)
        
        write_head = 0
        for read_head in range(N):
            if read_head > 0 and nums[read_head] == nums[read_head - 1]:
                continue
            nums[write_head] = nums[read_head]
            write_head = write_head + 1
            
        return write_head
```
