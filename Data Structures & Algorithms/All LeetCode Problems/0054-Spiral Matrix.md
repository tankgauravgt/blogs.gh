---
title: "0054: Spiral Matrix"
tags:
  - Array
  - Matrix
  - Simulation
---
### Problem Statement

<p>Given an <code>m x n</code> <code>matrix</code>, return <em>all elements of the</em> <code>matrix</code> <em>in spiral order</em>.</p>


<p><strong class="example">Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/11/13/spiral1.jpg" style="width: 242px; height: 242px;" />
<pre>
<strong>Input:</strong> matrix = [[1,2,3],[4,5,6],[7,8,9]]
<strong>Output:</strong> [1,2,3,6,9,8,7,4,5]
</pre>

<p><strong class="example">Example 2:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/11/13/spiral.jpg" style="width: 322px; height: 242px;" />
<pre>
<strong>Input:</strong> matrix = [[1,2,3,4],[5,6,7,8],[9,10,11,12]]
<strong>Output:</strong> [1,2,3,4,8,12,11,10,9,5,6,7]
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>m == matrix.length</code></li>
	<li><code>n == matrix[i].length</code></li>
	<li><code>1 &lt;= m, n &lt;= 10</code></li>
	<li><code>-100 &lt;= matrix[i][j] &lt;= 100</code></li>
</ul>


### Code Solution

```python
class Solution:
    def spiralOrder(self, matrix):
	    
        nR = len(matrix)
        nC = len(matrix[0])
        
        initR = 0
        initC = 0
        stopR = nR - 1
        stopC = nC - 1
        
        out = []
        count = 0
        while count < nR * nC:
            
            if count < nR * nC:
                for cx in range(initC, stopC + 1, +1):
                    out.append(matrix[initR][cx])
                    count = count + 1
                initR = initR + 1
            if count < nR * nC:
                for rx in range(initR, stopR + 1, +1):
                    out.append(matrix[rx][stopC])
                    count = count + 1
                stopC = stopC - 1
            if count < nR * nC:
                for cx in range(stopC, initC - 1, -1):
                    out.append(matrix[stopR][cx])
                    count = count + 1
                stopR = stopR - 1
            if count < nR * nC:
                for rx in range(stopR, initR - 1, -1):
                    out.append(matrix[rx][initC])
                    count = count + 1
                initC = initC + 1
        
        return out
```
