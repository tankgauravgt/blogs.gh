---
title: "0024: Swap Nodes in Pairs"
tags:
  - LinkedList
  - Recursion
---
### Problem Statement

<p>Given a linked list, swap every two adjacent nodes and return its head. You must solve the problem without modifying the values in the list&#39;s nodes (i.e., only nodes themselves may be changed.)</p>


<p><strong class="example">Example 1:</strong></p>

<div class="example-block">
<p><strong>Input:</strong> <span class="example-io">head = [1,2,3,4]</span></p>

<p><strong>Output:</strong> <span class="example-io">[2,1,4,3]</span></p>

<p><strong>Explanation:</strong></p>

<p><img alt="" src="https://assets.leetcode.com/uploads/2020/10/03/swap_ex1.jpg" style="width: 422px; height: 222px;" /></p>
</div>

<p><strong class="example">Example 2:</strong></p>

<div class="example-block">
<p><strong>Input:</strong> <span class="example-io">head = []</span></p>

<p><strong>Output:</strong> <span class="example-io">[]</span></p>
</div>

<p><strong class="example">Example 3:</strong></p>

<div class="example-block">
<p><strong>Input:</strong> <span class="example-io">head = [1]</span></p>

<p><strong>Output:</strong> <span class="example-io">[1]</span></p>
</div>

<p><strong class="example">Example 4:</strong></p>

<div class="example-block">
<p><strong>Input:</strong> <span class="example-io">head = [1,2,3]</span></p>

<p><strong>Output:</strong> <span class="example-io">[2,1,3]</span></p>
</div>


<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the list is in the range <code>[0, 100]</code>.</li>
	<li><code>0 &lt;= Node.val &lt;= 100</code></li>
</ul>


### Code Solution

```python
class Solution:
    def swapPairs(self, head: Optional[ListNode]) -> Optional[ListNode]:
        
        head = temp = ListNode(-1, head)
        while temp and temp.next and temp.next.next:
            node_plus_1 = temp.next
            node_plus_2 = temp.next.next
            node_plus_3 = temp.next.next.next
            
            node_plus_1.next = node_plus_3
            node_plus_2.next = node_plus_1
            temp.next = node_plus_2
            
            temp = temp.next.next
	        
        return head.next
```
