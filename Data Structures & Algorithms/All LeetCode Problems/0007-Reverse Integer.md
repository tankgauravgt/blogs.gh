---
title: "0007: Reverse Integer"
tags:
  - Math
---
### Problem Statement

<p>Given a signed 32-bit integer <code>x</code>, return <code>x</code><em> with its digits reversed</em>. If reversing <code>x</code> causes the value to go outside the signed 32-bit integer range <code>[-2<sup>31</sup>, 2<sup>31</sup> - 1]</code>, then return <code>0</code>.</p>

<p><strong>Assume the environment does not allow you to store 64-bit integers (signed or unsigned).</strong></p>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> x = 123
<strong>Output:</strong> 321
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> x = -123
<strong>Output:</strong> -321
</pre>

<p><strong class="example">Example 3:</strong></p>

<pre>
<strong>Input:</strong> x = 120
<strong>Output:</strong> 21
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>-2<sup>31</sup> &lt;= x &lt;= 2<sup>31</sup> - 1</code></li>
</ul>


### Code Solution

```python
class Solution:
    def reverse(self, x: int) -> int:
        
        # record the sign
        sign = -1 if x < 0 else +1
        
        # set limits without overflowing the values
        limit = 2 ** 30 + ((2 ** 30) - 1) if sign == +1 else 2 ** 31
        
        x = abs(x)
        
        cnum = 0
        while x:
            
            # look ahead if overflow can happen
            if cnum > limit // 10:
                return 0
            
            # corner case for overflow comparing last digit
            if cnum == limit // 10 and (x % 10 > limit % 10):
                return 0
            
            # update the value:
            cnum = cnum * 10 + (x % 10)
            x = x // 10
        
        return sign * cnum
```
