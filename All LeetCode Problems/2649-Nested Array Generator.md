---
title: "2649: Nested Array Generator"
tags:
---
### Problem Statement

<p>Given a <strong>multi-dimensional array</strong> of integers, return a generator object which yields integers in the same order as <strong>inorder traversal</strong>.</p>

<p>A <strong>multi-dimensional array</strong> is a recursive data structure that contains both integers and other <strong>multi-dimensional arrays</strong>.</p>

<p><strong>inorder traversal</strong> iterates over each array from left to right, yielding any integers it encounters or applying <strong>inorder traversal</strong> to any arrays it encounters.</p>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> arr = [[[6]],[1,3],[]]
<strong>Output:</strong> [6,1,3]
<strong>Explanation:</strong>
const generator = inorderTraversal(arr);
generator.next().value; // 6
generator.next().value; // 1
generator.next().value; // 3
generator.next().done; // true
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> arr = []
<strong>Output:</strong> []
<strong>Explanation:</strong> There are no integers so the generator doesn&#39;t yield anything.
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>0 &lt;= arr.flat().length &lt;= 10<sup>5</sup></code></li>
	<li><code>0 &lt;= arr.flat()[i] &lt;= 10<sup>5</sup></code></li>
	<li><code>maxNestingDepth &lt;= 10<sup>5</sup></code></li>
</ul>


<strong>Can you solve this without creating a new flattened version of the array?</strong>

### Code Solution

```python

```
