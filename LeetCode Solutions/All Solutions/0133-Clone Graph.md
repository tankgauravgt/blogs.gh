---
title: "0133: Clone Graph"
---
```python
"""
# Definition for a Node.
class Node:
    def __init__(self, val = 0, neighbors = None):
        self.val = val
        self.neighbors = neighbors if neighbors is not None else []
"""

class Solution:
    def cloneGraph(self, node):
        vset = {}
        def dfs(root):
            if not root:
                return None
            vset[root] = Node(root.val, [])
            for adj in root.neighbors:
                if adj not in vset:
                    vset[adj] = dfs(adj)
                vset[root].neighbors.append(vset[adj])
            return vset[root]
        return dfs(node)
```
