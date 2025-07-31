---
title: "0297: Serialize and Deserialize Binary Tree"
---
```python
class Solution:
    def serialize(self, root):
        res = []
        def rec(node):
            nonlocal res
            if not node:
                res.append('x')
                return
            res.append(str(node.val))
            rec(node.left)
            rec(node.right)
        rec(root)
        return " ".join(res)
    
    def deserialize(self, data):
        
        def rec(it):
            v = next(it)
            if v == 'x':
                return None
            cnode = TreeNode(
                int(v),
                rec(it),
                rec(it)
            )
            return cnode
        
        temp = iter(data.split())
        return rec(temp)
```
