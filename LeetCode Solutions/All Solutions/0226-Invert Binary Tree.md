---
title: "0226: Invert Binary Tree"
---
```python
class Solution:
    def invertTree(self, root):
        def rec(node):
            if node:           
                a = node.left
                b = node.right
                node.left = b
                node.right = a
                rec(node.left)
                rec(node.right)
        
        rec(root)
        return root
```
