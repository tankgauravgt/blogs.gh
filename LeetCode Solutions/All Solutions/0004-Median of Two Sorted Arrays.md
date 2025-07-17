---
title: "0004: Median of Two Sorted Arrays"
tags:
  - Array
  - BinarySearch
  - DivideAndConquer
---
```python
class Solution:
    def findMedianSortedArrays(self, nums1, nums2):
        
        if len(nums1) > len(nums2): 
            nums1, nums2 = nums2, nums1
            
        NU, NL = len(nums1), len(nums2)
        lx, rx = 0, NU
        
        while lx <= rx:
        
            pxu = (lx + rx) // 2
            pxl = (NU + NL + 1) // 2 - pxu
            
            ul = float('-inf') if pxu == 0 else nums1[pxu - 1]
            ur = float('inf') if pxu == NU else nums1[pxu]
            
            ll = float('-inf') if pxl == 0 else nums2[pxl - 1]
            lr = float('inf') if pxl == NL else nums2[pxl]
            
            if ul <= lr and ll <= ur:
                if (NU + NL) % 2 == 0:
                    return (max(ul, ll) + min(ur, lr)) / 2
                return max(ul, ll)
            elif ul > lr:
                rx = pxu - 1
            else:
                lx = pxu + 1
                
        return -1
```
