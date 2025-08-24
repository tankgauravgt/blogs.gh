---
title: "0025: Reverse Nodes in k-Group"
tags:
  - LinkedList
  - Recursion
---
### Problem Statement

<p>Given the <code>head</code> of a linked list, reverse the nodes of the list <code>k</code> at a time, and return <em>the modified list</em>.</p>

<p><code>k</code> is a positive integer and is less than or equal to the length of the linked list. If the number of nodes is not a multiple of <code>k</code> then left-out nodes, in the end, should remain as it is.</p>

<p>You may not alter the values in the list&#39;s nodes, only nodes themselves may be changed.</p>


<p><strong class="example">Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/10/03/reverse_ex1.jpg" style="width: 542px; height: 222px;" />
<pre>
<strong>Input:</strong> head = [1,2,3,4,5], k = 2
<strong>Output:</strong> [2,1,4,3,5]
</pre>

<p><strong class="example">Example 2:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/10/03/reverse_ex2.jpg" style="width: 542px; height: 222px;" />
<pre>
<strong>Input:</strong> head = [1,2,3,4,5], k = 3
<strong>Output:</strong> [3,2,1,4,5]
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the list is <code>n</code>.</li>
	<li><code>1 &lt;= k &lt;= n &lt;= 5000</code></li>
	<li><code>0 &lt;= Node.val &lt;= 1000</code></li>
</ul>


<p><strong>Follow-up:</strong> Can you solve the problem in <code>O(1)</code> extra memory space?</p>


### Code Solution

```python
class Solution:
    def reverseKGroup(self, head, k):
	    
        def revk(node, k):
            prev = None
            curr = node
            while curr and k > 0:
                temp = curr.next
                curr.next = prev
                prev = curr
                curr = temp
                k = k - 1
            return prev, curr, k == 0
		
        dummy = ListNode(0)
        
        temp = dummy
        while head:
            done, head, completed = revk(head, k)
            temp.next = done if completed else revk(done, k)[0]
            while temp and temp.next:
                temp = temp.next
        return dummy.next
```
