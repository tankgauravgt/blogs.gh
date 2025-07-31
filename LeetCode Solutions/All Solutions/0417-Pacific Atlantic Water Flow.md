---
title: "0417: Pacific Atlantic Water Flow"
---
```python
from collections import deque

class Solution:
    def pacificAtlantic(self, heights):
        nR = len(heights)
        nC = len(heights[0])
        def bfs(iset):
            dq = deque(iset)
            vset = set(iset)
            cset = set()
            while dq:
                rx, cx = dq.popleft()
                cset.add((rx, cx))
                for dr, dc in [(0, 1), (1, 0), (0, -1), (-1, 0)]:
                    rr = rx + dr
                    cc = cx + dc
                    if 0 <= rr < nR and 0 <= cc < nC:
                        if heights[rr][cc] >= heights[rx][cx] and (rr, cc) not in vset:
                            vset.add((rr, cc))
                            dq.append((rr, cc))
            return cset
        pac = set()
        atl = set()
        for rx in range(nR):
            pac.add((rx, 0))
            atl.add((rx, nC - 1))
        for cx in range(nC):
            pac.add((0, cx))
            atl.add((nR - 1, cx))
        P = bfs(pac)
        A = bfs(atl)
        res = P & A
```
