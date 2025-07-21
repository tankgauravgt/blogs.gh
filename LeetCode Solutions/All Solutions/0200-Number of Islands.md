---
title: "0200: Number of Islands"
---
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
