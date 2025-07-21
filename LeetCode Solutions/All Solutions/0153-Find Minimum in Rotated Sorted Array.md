---
title: "0153: Find Minimum in Rotated Sorted Array"
---
```python
import bisect

class Solution:
    def findMin(self, nums):
        def bsearch(arr, lx, rx, target):
            if lx <= rx:
                mx = lx + (rx - lx) // 2
                if int(arr[mx] < nums[0]) < target:
                    return bsearch(arr, mx + 1, rx, target)
                else:
                    temp = bsearch(arr, lx, mx - 1, target)
                    if temp == -1:
                        return mx
                    return temp
            return -1
        ix = bsearch(nums, 0, len(nums) - 1, 0.5)
        if ix == -1:
            return nums[0]
        return nums[ix % len(nums)]
```
