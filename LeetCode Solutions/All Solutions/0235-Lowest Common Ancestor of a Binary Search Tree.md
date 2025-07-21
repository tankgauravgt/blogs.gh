---
title: "0235: Lowest Common Ancestor of a Binary Search Tree"
---
```python
class Solution:
    def lowestCommonAncestor(self, root, p, q):

        def rec(node, p, q):
            if not node or node == p or node == q:
                return node
				
            flagL = rec(node.left, p, q)
            flagR = rec(node.right, p, q)
				
            if flagL and flagR:
                return node
	            
            return flagL or flagR
            
        return rec(root, p, q)
```
