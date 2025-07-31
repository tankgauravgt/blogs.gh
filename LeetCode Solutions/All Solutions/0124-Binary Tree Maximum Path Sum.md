---
title: "0124: Binary Tree Maximum Path Sum"
---
```python
class Solution:
    def maxPathSum(self, root):
	    
        cmax = float('-inf')
        def rec(node):
            nonlocal cmax
            if not node:
                return 0
            lsum = max(0, rec(node.left))
            rsum = max(0, rec(node.right))
            cmax = max(cmax, node.val + lsum + rsum)
            return node.val + max(lsum, rsum)
        
        rec(root)
        return cmax
```
