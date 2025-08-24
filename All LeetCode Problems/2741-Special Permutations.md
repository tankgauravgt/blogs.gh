---
title: "2741: Special Permutations"
tags:
  - Array
  - DynamicProgramming
  - BitManipulation
  - Bitmask
---
### Problem Statement

<p>You are given a <strong>0-indexed</strong> integer array <code>nums</code> containing <code>n</code> <strong>distinct</strong> positive integers. A permutation of <code>nums</code> is called special if:</p>

<ul>
	<li>For all indexes <code>0 &lt;= i &lt; n - 1</code>, either <code>nums[i] % nums[i+1] == 0</code> or <code>nums[i+1] % nums[i] == 0</code>.</li>
</ul>

<p>Return <em>the total number of special permutations. </em>As the answer could be large, return it <strong>modulo </strong><code>10<sup>9 </sup>+ 7</code>.</p>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> nums = [2,3,6]
<strong>Output:</strong> 2
<strong>Explanation:</strong> [3,6,2] and [2,6,3] are the two special permutations of nums.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> nums = [1,4,3]
<strong>Output:</strong> 2
<strong>Explanation:</strong> [3,1,4] and [4,1,3] are the two special permutations of nums.
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>2 &lt;= nums.length &lt;= 14</code></li>
	<li><code>1 &lt;= nums[i] &lt;= 10<sup>9</sup></code></li>
</ul>


### Code Solution

```python

```
