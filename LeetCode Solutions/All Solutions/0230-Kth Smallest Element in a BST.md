---
title: "0230: Kth Smallest Element in a BST"
---
```python
class Solution:
    def kthSmallest(self, root, k):
	    
        res = None
        def rec(node):
            nonlocal res, k
            if not node:
                return
            rec(node.left)
            if k == 1:
                res = node.val
                k = k - 1
                return
            k = k - 1
            rec(node.right)
        
        rec(root)
        return res
```