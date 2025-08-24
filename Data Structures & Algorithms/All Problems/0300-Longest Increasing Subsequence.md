---
title: "0300: Longest Increasing Subsequence"
tags:
  - Array
  - BinarySearch
  - DynamicProgramming
---
### Problem Statement

<p>Given an integer array <code>nums</code>, return <em>the length of the longest <strong>strictly increasing </strong></em><span data-keyword="subsequence-array"><em><strong>subsequence</strong></em></span>.</p>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> nums = [10,9,2,5,3,7,101,18]
<strong>Output:</strong> 4
<strong>Explanation:</strong> The longest increasing subsequence is [2,3,7,101], therefore the length is 4.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> nums = [0,1,0,3,2,3]
<strong>Output:</strong> 4
</pre>

<p><strong class="example">Example 3:</strong></p>

<pre>
<strong>Input:</strong> nums = [7,7,7,7,7,7,7]
<strong>Output:</strong> 1
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 2500</code></li>
	<li><code>-10<sup>4</sup> &lt;= nums[i] &lt;= 10<sup>4</sup></code></li>
</ul>


<p><b>Follow up:</b> Can you come up with an algorithm that runs in <code>O(n log(n))</code> time complexity?</p>


### Code Solution

```python
class Solution:
    def lengthOfLIS(self, nums):
        N = len(nums)
        
        # Maximum of below iterations:
        #     (sx + 1): [..., sx - 1] <sx> [sx + 1, ..., N - 1]
        #     (sx + 2): [..., sx - 1] <sx> [sx + 2, ..., N - 1]
        #     (sx + 3): .......................................
        # (sx + N - 1): [..., sx - 1] <sx> [sx + N, ..., N - 1]
        
        @cache
        def rec(sx):
            if sx == N:
                return 0
            cmax = 1
            for ix in range(sx + 1, N, 1):
                if nums[ix] > nums[sx]:
                    cmax = max(cmax, 1 + rec(ix))
            return cmax
        
        # Perform LIS starting from all indices:
        return max([rec(ix) for ix in range(N)])
```
