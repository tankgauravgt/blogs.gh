---
title: "0098: Validate Binary Search Tree"
---
```python
class Solution:
    def isValidBST(self, root):
        def rec(node, lmax, rmin):
            if not node:
                return True
            if node.val <= lmax or node.val >= rmin:
                return False
            return rec(node.left, lmax, node.val) and rec(node.right, node.val, rmin)

        return rec(root, float('-inf'), float('+inf'))
```
