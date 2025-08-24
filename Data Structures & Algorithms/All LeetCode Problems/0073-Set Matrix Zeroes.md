---
title: "0073: Set Matrix Zeroes"
tags:
  - Array
  - HashTable
  - Matrix
---
### Problem Statement

<p>Given an <code>m x n</code> integer matrix <code>matrix</code>, if an element is <code>0</code>, set its entire row and column to <code>0</code>&#39;s.</p>

<p>You must do it <a href="https://en.wikipedia.org/wiki/In-place_algorithm" target="_blank">in place</a>.</p>


<p><strong class="example">Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/08/17/mat1.jpg" style="width: 450px; height: 169px;" />
<pre>
<strong>Input:</strong> matrix = [[1,1,1],[1,0,1],[1,1,1]]
<strong>Output:</strong> [[1,0,1],[0,0,0],[1,0,1]]
</pre>

<p><strong class="example">Example 2:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/08/17/mat2.jpg" style="width: 450px; height: 137px;" />
<pre>
<strong>Input:</strong> matrix = [[0,1,2,0],[3,4,5,2],[1,3,1,5]]
<strong>Output:</strong> [[0,0,0,0],[0,4,5,0],[0,3,1,0]]
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>m == matrix.length</code></li>
	<li><code>n == matrix[0].length</code></li>
	<li><code>1 &lt;= m, n &lt;= 200</code></li>
	<li><code>-2<sup>31</sup> &lt;= matrix[i][j] &lt;= 2<sup>31</sup> - 1</code></li>
</ul>


<p><strong>Follow up:</strong></p>

<ul>
	<li>A straightforward solution using <code>O(mn)</code> space is probably a bad idea.</li>
	<li>A simple improvement uses <code>O(m + n)</code> space, but still not the best solution.</li>
	<li>Could you devise a constant space solution?</li>
</ul>


### Code Solution

```python
class Solution:
    def setZeroes(self, matrix):
	    
        nR = len(matrix)
        nC = len(matrix[0])
        
        hasRow0 = False
        hasCol0 = False
        
        m = matrix
        for rx in range(nR):
            if m[rx][0] == 0:
                hasCol0 = True
        
        for cx in range(nC):
            if m[0][cx] == 0:
                hasRow0 = True
        
        for rx in range(1, nR):
            for cx in range(1, nC):
                if m[rx][cx] == 0:
                    m[0][cx] = 0
                    m[rx][0] = 0
        
        for rx in range(1, nR):
            if m[rx][0] == 0:
                for cx in range(1, nC):
                    m[rx][cx] = 0
        
        for cx in range(1, nC):
            if m[0][cx] == 0:
                for rx in range(1, nR):
                    m[rx][cx] = 0
        
        if hasRow0:
            for cx in range(nC):
                m[0][cx] = 0
        if hasCol0:
            for rx in range(nR):
                m[rx][0] = 0
```
