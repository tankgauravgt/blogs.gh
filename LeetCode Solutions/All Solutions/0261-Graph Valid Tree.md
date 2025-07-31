---
title: "0261: Graph Valid Tree"
---
```python
from collections import deque

class Solution:
    def validTree(self, n, edges):
        G = {ix: [] for ix in range(n)}
        for uv in edges:
            u, v = uv[0], uv[1]
            G[u].append(v)
            G[v].append(u)
        dq = deque([0])
        vset = set([0])
        ctr = 0
        while dq:
            curr = dq.popleft()
            ctr = ctr + 1
            for adj in G[curr]:
                if adj not in vset:
                    vset.add(adj)
                    dq.append(adj)
        return len(edges) == n - 1 and ctr == n
```
