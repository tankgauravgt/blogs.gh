---
title: "0004: Median of Two Sorted Arrays"
tags:
  - Array
  - BinarySearch
  - DivideandConquer
---
### Problem Statement

<p>Given two sorted arrays <code>nums1</code> and <code>nums2</code> of size <code>m</code> and <code>n</code> respectively, return <strong>the median</strong> of the two sorted arrays.</p>

<p>The overall run time complexity should be <code>O(log (m+n))</code>.</p>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> nums1 = [1,3], nums2 = [2]
<strong>Output:</strong> 2.00000
<strong>Explanation:</strong> merged array = [1,2,3] and median is 2.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> nums1 = [1,2], nums2 = [3,4]
<strong>Output:</strong> 2.50000
<strong>Explanation:</strong> merged array = [1,2,3,4] and median is (2 + 3) / 2 = 2.5.
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>nums1.length == m</code></li>
	<li><code>nums2.length == n</code></li>
	<li><code>0 &lt;= m &lt;= 1000</code></li>
	<li><code>0 &lt;= n &lt;= 1000</code></li>
	<li><code>1 &lt;= m + n &lt;= 2000</code></li>
	<li><code>-10<sup>6</sup> &lt;= nums1[i], nums2[i] &lt;= 10<sup>6</sup></code></li>
</ul>


### Code Solution

```python
class Solution:
	
    def get_extremes(self, arr, p, n):
        lmax = float('-inf') if p == 0 else arr[p - 1]
        rmin = float('+inf') if p == n else arr[p]
        return lmax, rmin
		
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        # s1: assure len(nums1) > len(nums2)
        # s2: figure out pivots
        # s3: find boundary elements (`upr_lmax`, `upr_rmin`, `btm_lmax`, `btm_rmin`)
        # s4: converge and return median
        
        
        # s1: assure len(nums1) > len(nums2)
        if len(nums1) > len(nums2):
            nums1, nums2 = nums2, nums1
			
        nU, nL = len(nums1), len(nums2)
        
        lx = 0
        rx = nU
        while lx <= rx:
	        
            # s2: calculate pivots:
            p1 = (lx + rx) // 2
            p2 = (nU + nL + 1) // 2 - p1
            
            # s3: find boundaries:
            upr_lmax, upr_rmin = self.get_extremes(nums1, p1, nU)
            btm_lmax, btm_rmin = self.get_extremes(nums2, p2, nL)            
            
            # s4: converge and return median:
            if max(upr_lmax, btm_lmax) <= min(upr_rmin, btm_rmin):
                if (nL + nU) % 2 == 0:
                    return (max(upr_lmax, btm_lmax) + min(upr_rmin, btm_rmin)) / 2
                else:
                    return max(upr_lmax, btm_lmax)
            else:
                if btm_rmin < upr_lmax:
                    rx = p1 - 1
                elif upr_rmin < btm_lmax:
                    lx = p1 + 1		    
        return -1
```
