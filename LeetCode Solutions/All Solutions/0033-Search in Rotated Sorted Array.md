---
title: "0033: Search in Rotated Sorted Array"
---
```python
class Solution:
    def search(self, nums, target):
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
        ix = ix % len(nums) if ix != -1 else 0
        imap = lambda x: (x + ix) % len(nums)
        N = len(nums)
        def binsearch(arr, lx, rx, target):
            if lx <= rx:
                mx = lx + (rx - lx) // 2
                if arr[imap(mx)] == target:
                    return imap(mx)
                elif arr[imap(mx)] < target:
                    return binsearch(arr, mx + 1, rx, target)
                else:
                    return binsearch(arr, lx, mx - 1, target)
            return -1
```
