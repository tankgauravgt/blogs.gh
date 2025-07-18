---
title: "0016: 3Sum Closest"
---
```python
class Solution:
    def threeSumClosest(self, nums, target):
        nums.sort()
        cmin = float('inf')
        for ix in range(len(nums) - 2):
            lx = ix + 1
            rx = len(nums) - 1
            while lx < rx:
                csum = nums[ix] + nums[lx] + nums[rx]
                if csum == target: return csum
                cmin = min(cmin, csum, key=lambda x: abs(target - x))
                if csum <= target:
                    lx += 1
                else:
                    rx -= 1
        return cmin
```
