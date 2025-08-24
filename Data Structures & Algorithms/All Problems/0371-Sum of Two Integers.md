---
title: "0371: Sum of Two Integers"
tags:
  - Math
  - BitManipulation
---
### Problem Statement

<p>Given two integers <code>a</code> and <code>b</code>, return <em>the sum of the two integers without using the operators</em> <code>+</code> <em>and</em> <code>-</code>.</p>


<p><strong class="example">Example 1:</strong></p>
<pre><strong>Input:</strong> a = 1, b = 2
<strong>Output:</strong> 3
</pre><p><strong class="example">Example 2:</strong></p>
<pre><strong>Input:</strong> a = 2, b = 3
<strong>Output:</strong> 5
</pre>

<p><strong>Constraints:</strong></p>

<ul>
	<li><code>-1000 &lt;= a, b &lt;= 1000</code></li>
</ul>


### Code Solution

```python
class Solution:
    def getSum(self, a, b):
        MASK = 0xFFFFFFFF
        acc = a
        bfr = b
        while bfr:
            carry = ((acc & bfr) << 1) & MASK
            sum_without_carry = (acc ^ bfr) & MASK
            acc = sum_without_carry
            bfr = carry
        return acc if acc <= 2 ** 31 - 1 else ~(acc ^ MASK)
```
