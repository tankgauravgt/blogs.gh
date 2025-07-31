---
title: "0102: Binary Tree Level Order Traversal"
---
```python
from collections import deque

class Solution:
    def levelOrder(self, root):
	    
        if not root:
            return []
        
        dq = deque([root])
        
        out = []
        while dq:
            N = len(dq)
            temp = []
            for _ in range(N):
                curr = dq.popleft()
                temp.append(curr.val)
                if curr.left: dq.append(curr.left)
                if curr.right: dq.append(curr.right)
            out.append(temp)
        return out
```