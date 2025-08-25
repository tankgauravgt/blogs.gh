---
title: "0029: Divide Two Integers"
tags:
  - Math
  - BitManipulation
---
### Problem Statement

<p>Given two integers <code>dividend</code> and <code>divisor</code>, divide two integers <strong>without</strong> using multiplication, division, and mod operator.</p>

<p>The integer division should truncate toward zero, which means losing its fractional part. For example, <code>8.345</code> would be truncated to <code>8</code>, and <code>-2.7335</code> would be truncated to <code>-2</code>.</p>

<p>Return <em>the <strong>quotient</strong> after dividing </em><code>dividend</code><em> by </em><code>divisor</code>.</p>

<p><strong>Note: </strong>Assume we are dealing with an environment that could only store integers within the <strong>32-bit</strong> signed integer range: <code>[&minus;2<sup>31</sup>, 2<sup>31</sup> &minus; 1]</code>. For this problem, if the quotient is <strong>strictly greater than</strong> <code>2<sup>31</sup> - 1</code>, then return <code>2<sup>31</sup> - 1</code>, and if the quotient is <strong>strictly less than</strong> <code>-2<sup>31</sup></code>, then return <code>-2<sup>31</sup></code>.</p>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> dividend = 10, divisor = 3
<strong>Output:</strong> 3
<strong>Explanation:</strong> 10/3 = 3.33333.. which is truncated to 3.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> dividend = 7, divisor = -3
<strong>Output:</strong> -2
<strong>Explanation:</strong> 7/-3 = -2.33333.. which is truncated to -2.
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>-2<sup>31</sup> &lt;= dividend, divisor &lt;= 2<sup>31</sup> - 1</code></li>
	<li><code>divisor != 0</code></li>
</ul>


### Code Solution

```python
class Solution:
    def divide(self, dividend, divisor):
        MIN_VAL, MAX_VAL = -(2 ** 31), +(2 ** 31 - 1)
        
        # Edge case: (MIN_VAL / -1) overflows.
        if dividend == MIN_VAL and divisor == -1:
            return MAX_VAL
        
        sign = -1 if (dividend < 0) ^ (divisor < 0) else +1
        
        a = abs(dividend)
        b = abs(divisor)
        
        res = 0
        for ix in range(31, -1, -1):
            temp = (b << ix)
            
            if a >= temp:
                a = a - temp
                res = res + (1 << ix)
        
        return -res if sign == -1 else res
```
