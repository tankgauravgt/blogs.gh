---
title: "0105: Construct Binary Tree from Preorder and Inorder Traversal"
---
```python
class Solution:
    def buildTree(self, preorder, inorder):
	    
        def rec(po, io):
            if not po:
                return None
            ix = io.index(po[0])
            return TreeNode(
                po[0],
                rec(po[1:1+ix], io[0:ix]),
                rec(po[1+ix:], io[1+ix:])
            )
        
        return rec(preorder, inorder)
```