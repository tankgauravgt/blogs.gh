---
title: "0104: Maximum Depth of Binary Tree"
---
```python
class Solution:
    def maxDepth(self, root):
        def rec(node):
            if not node:
                return 0
            return 1 + max(rec(node.left), rec(node.right))
        return rec(root) if root else 0
```
