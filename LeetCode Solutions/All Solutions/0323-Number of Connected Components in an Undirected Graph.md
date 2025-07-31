---
title: "0323: Number of Connected Components in an Undirected Graph"
---
```python
from collections import deque

class Solution:
    def countComponents(self, n, edges):
	    
        G = {ix: [] for ix in range(n)}
        
        for uv in edges:
            u, v = uv[0], uv[1]
            G[u].append(v)
            G[v].append(u)
	    
        def bfs(init, vset):
            vset.add(init)
            dq = deque([init])
            while dq:
                curr = dq.popleft()
                for adj in G[curr]:
                    if adj not in vset:
                        vset.add(adj)
                        dq.append(adj)
        
        count = 0
        cache = set()
        for ix in range(n):
            if ix not in cache:
                bfs(ix, cache)
                count = count + 1
        
        return count
```
