---
title: "1282: Group the People Given the Group Size They Belong To"
tags:
  - Array
  - HashTable
  - Greedy
---
### Problem Statement

<p>There are <code>n</code> people that are split into some unknown number of groups. Each person is labeled with a <strong>unique ID</strong> from <code>0</code> to <code>n - 1</code>.</p>

<p>You are given an integer array <code>groupSizes</code>, where <code>groupSizes[i]</code> is the size of the group that person <code>i</code> is in. For example, if <code>groupSizes[1] = 3</code>, then person <code>1</code> must be in a group of size <code>3</code>.</p>

<p>Return <em>a list of groups such that each person <code>i</code> is in a group of size <code>groupSizes[i]</code></em>.</p>

<p>Each person should appear in <strong>exactly one group</strong>, and every person must be in a group. If there are multiple answers, <strong>return any of them</strong>. It is <strong>guaranteed</strong> that there will be <strong>at least one</strong> valid solution for the given input.</p>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> groupSizes = [3,3,3,3,3,1,3]
<strong>Output:</strong> [[5],[0,1,2],[3,4,6]]
<b>Explanation:</b> 
The first group is [5]. The size is 1, and groupSizes[5] = 1.
The second group is [0,1,2]. The size is 3, and groupSizes[0] = groupSizes[1] = groupSizes[2] = 3.
The third group is [3,4,6]. The size is 3, and groupSizes[3] = groupSizes[4] = groupSizes[6] = 3.
Other possible solutions are [[2,1,6],[5],[0,4,3]] and [[5],[0,6,2],[4,3,1]].
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> groupSizes = [2,1,3,3,3,2]
<strong>Output:</strong> [[1],[0,5],[2,3,4]]
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>groupSizes.length == n</code></li>
	<li><code>1 &lt;= n &lt;= 500</code></li>
	<li><code>1 &lt;= groupSizes[i] &lt;= n</code></li>
</ul>


### Code Solution

```python

```
