---
title: "0102: Binary Tree Level Order Traversal"
tags:
  - Tree
  - Breadth-FirstSearch
  - BinaryTree
---
### Problem Statement

<p>Given the <code>root</code> of a binary tree, return <em>the level order traversal of its nodes&#39; values</em>. (i.e., from left to right, level by level).</p>


<p><strong class="example">Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2021/02/19/tree1.jpg" style="width: 277px; height: 302px;" />
<pre>
<strong>Input:</strong> root = [3,9,20,null,null,15,7]
<strong>Output:</strong> [[3],[9,20],[15,7]]
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> root = [1]
<strong>Output:</strong> [[1]]
</pre>

<p><strong class="example">Example 3:</strong></p>

<pre>
<strong>Input:</strong> root = []
<strong>Output:</strong> []
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the tree is in the range <code>[0, 2000]</code>.</li>
	<li><code>-1000 &lt;= Node.val &lt;= 1000</code></li>
</ul>


### Code Solution

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
