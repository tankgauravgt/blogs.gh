---
title: "1433: Check If a String Can Break Another String"
tags:
  - String
  - Greedy
  - Sorting
---
### Problem Statement

<p>Given two strings: <code>s1</code> and <code>s2</code> with the same size, check if some permutation of string <code>s1</code> can break some permutation of string <code>s2</code> or vice-versa. In other words <code>s2</code> can break <code>s1</code> or vice-versa.</p>

<p>A string <code>x</code> can break string <code>y</code> (both of size <code>n</code>) if <code>x[i] &gt;= y[i]</code> (in alphabetical order) for all <code>i</code> between <code>0</code> and <code>n-1</code>.</p>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> s1 = &quot;abc&quot;, s2 = &quot;xya&quot;
<strong>Output:</strong> true
<strong>Explanation:</strong> &quot;ayx&quot; is a permutation of s2=&quot;xya&quot; which can break to string &quot;abc&quot; which is a permutation of s1=&quot;abc&quot;.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> s1 = &quot;abe&quot;, s2 = &quot;acd&quot;
<strong>Output:</strong> false 
<strong>Explanation:</strong> All permutations for s1=&quot;abe&quot; are: &quot;abe&quot;, &quot;aeb&quot;, &quot;bae&quot;, &quot;bea&quot;, &quot;eab&quot; and &quot;eba&quot; and all permutation for s2=&quot;acd&quot; are: &quot;acd&quot;, &quot;adc&quot;, &quot;cad&quot;, &quot;cda&quot;, &quot;dac&quot; and &quot;dca&quot;. However, there is not any permutation from s1 which can break some permutation from s2 and vice-versa.
</pre>

<p><strong class="example">Example 3:</strong></p>

<pre>
<strong>Input:</strong> s1 = &quot;leetcodee&quot;, s2 = &quot;interview&quot;
<strong>Output:</strong> true
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>s1.length == n</code></li>
	<li><code>s2.length == n</code></li>
	<li><code>1 &lt;= n &lt;= 10^5</code></li>
	<li>All strings consist of lowercase English letters.</li>
</ul>


### Code Solution

```python

```
