---
title: "0200: Number of Islands"
tags:
  - Array
  - Depth-FirstSearch
  - Breadth-FirstSearch
  - UnionFind
  - Matrix
---
### Problem Statement

<p>Given an <code>m x n</code> 2D binary grid <code>grid</code> which represents a map of <code>&#39;1&#39;</code>s (land) and <code>&#39;0&#39;</code>s (water), return <em>the number of islands</em>.</p>

<p>An <strong>island</strong> is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.</p>


<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> grid = [
  [&quot;1&quot;,&quot;1&quot;,&quot;1&quot;,&quot;1&quot;,&quot;0&quot;],
  [&quot;1&quot;,&quot;1&quot;,&quot;0&quot;,&quot;1&quot;,&quot;0&quot;],
  [&quot;1&quot;,&quot;1&quot;,&quot;0&quot;,&quot;0&quot;,&quot;0&quot;],
  [&quot;0&quot;,&quot;0&quot;,&quot;0&quot;,&quot;0&quot;,&quot;0&quot;]
]
<strong>Output:</strong> 1
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> grid = [
  [&quot;1&quot;,&quot;1&quot;,&quot;0&quot;,&quot;0&quot;,&quot;0&quot;],
  [&quot;1&quot;,&quot;1&quot;,&quot;0&quot;,&quot;0&quot;,&quot;0&quot;],
  [&quot;0&quot;,&quot;0&quot;,&quot;1&quot;,&quot;0&quot;,&quot;0&quot;],
  [&quot;0&quot;,&quot;0&quot;,&quot;0&quot;,&quot;1&quot;,&quot;1&quot;]
]
<strong>Output:</strong> 3
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li><code>m == grid.length</code></li>
	<li><code>n == grid[i].length</code></li>
	<li><code>1 &lt;= m, n &lt;= 300</code></li>
	<li><code>grid[i][j]</code> is <code>&#39;0&#39;</code> or <code>&#39;1&#39;</code>.</li>
</ul>


### Code Solution

```python
from collections import deque

class Solution:
    def numIslands(self, grid):
        nR = len(grid)
        nC = len(grid[0])
        def bfs(rx, cx, vset):
            dq = deque([(rx, cx)])
            vset.add((rx, cx))
            while dq:
                rr, cc = dq.popleft()
                for dr, dc in [(0, 1), (1, 0), (-1, 0), (0, -1)]:
                    nr = rr + dr
                    nc = cc + dc
                    if 0 <= nr < nR and 0 <= nc < nC:
                        if grid[nr][nc] == "1" and (nr, nc) not in vset:
                            vset.add((nr, nc))
                            dq.append((nr, nc))
        count = 0
        cache = set()
        for ir in range(nR):
            for ic in range(nC):
                if grid[ir][ic] == "1" and (ir, ic) not in cache:
                    bfs(ir, ic, cache)
                    count = count + 1
        return count
```
