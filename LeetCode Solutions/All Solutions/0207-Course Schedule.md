---
title: "0207: Course Schedule"
---
```python
from collections import deque

class Solution:
    def canFinish(self, numCourses, prerequisites):
        G = {ix: [] for ix in range(numCourses)}
        P = {ix: 0 for ix in range(numCourses)}
        for pr in prerequisites:
            v, u = pr[0], pr[1]
            G[u].append(v)
            P[v] = P[v] + 1
        iset = []
        for ix in P:
            if P[ix] == 0:
                iset.append(ix)
        dq = deque(iset)
        vset = set(iset)
        count = 0
        while dq:
            curr = dq.popleft()
            count = count + 1
            for adj in G[curr]:
                P[adj] = P[adj] - 1
                if P[adj] == 0:
                    if adj not in vset:
                        vset.add(adj)
                        dq.append(adj)
        return count == numCourses
```
