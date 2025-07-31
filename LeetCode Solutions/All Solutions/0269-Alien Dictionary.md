---
title: "0269: Alien Dictionary"
---
```python
from collections import deque

class Solution:
    def foreignDict(self, words):
        G = {c: set() for c in "".join(words)}
        P = {c: 0 for c in G}
        for wx, w2 in enumerate(words):
            if wx == 0:
                continue
            w1 = words[wx - 1]
            p1 = 0
            p2 = 0
            while p1 < len(w1) and p2 < len(w2):
                if w1[p1] == w2[p2]:
                    p1 = p1 + 1
                    p2 = p2 + 1
                else:
                    G[w1[p1]].add(w2[p2])
                    break
        
        for u in G:
            for v in G[u]:
                P[v] = P[v] + 1
        
        init = []
        for e in P:
            if P[e] == 0:
                init.append(e)
        
        dq = deque(init)
        vset = set(init)
        
        res = []
        while dq:
            curr = dq.popleft()
            res.append(curr)
            for adj in G[curr]:
                P[adj] -= 1
                if P[adj] == 0:
                    vset.add(adj)
                    dq.append(adj)
        
        return "".join(res)
```
