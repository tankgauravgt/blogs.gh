---
title: "0041: First Missing Positive"
tags:
  - Array
  - HashTable
---
### Problem Statement

<p>Given an unsorted integer array <code>nums</code>. Return the <em>smallest positive integer</em> that is <em>not present</em> in <code>nums</code>.</p>

<p>You must implement an algorithm that runs in <code>O(n)</code> time and uses <code>O(1)</code> auxiliary space.</p>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> nums = [1,2,0]
<strong>Output:</strong> 3
<strong>Explanation:</strong> The numbers in the range [1,2] are all in the array.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> nums = [3,4,-1,1]
<strong>Output:</strong> 2
<strong>Explanation:</strong> 1 is in the array but 2 is missing.
</pre>

<p><strong class="example">Example 3:</strong></p>

<pre>
<strong>Input:</strong> nums = [7,8,9,11,12]
<strong>Output:</strong> 1
<strong>Explanation:</strong> The smallest positive integer 1 is missing.
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 10<sup>5</sup></code></li>
	<li><code>-2<sup>31</sup> &lt;= nums[i] &lt;= 2<sup>31</sup> - 1</code></li>
</ul>


### Code Solution

```python
class Solution:
    def firstMissingPositive(self, nums: List[int]) -> int:
        N = len(nums)
        
        # Steps:
        # ------
        # 1. Perform cyclic sort (arr[ix] = ix + 1)
        # 2. Write a checking loop
        
        # =================================================
        # perform cyclic sort:
        # =================================================
        
        ix = 0
        while ix < N:
            correct = nums[ix] - 1
            if 0 <= correct < N and nums[ix] != nums[correct]:
                nums[ix], nums[correct] = nums[correct], nums[ix]
                continue
            ix = ix + 1
        
        # =================================================
        # checking loop:
        # =================================================
        
        for ix in range(N):
            if nums[ix] != ix + 1:
                return ix + 1
        
        return N + 1
```
