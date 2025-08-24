---
title: "0021: Merge Two Sorted Lists"
tags:
  - LinkedList
  - Recursion
---
### Problem Statement

<p>You are given the heads of two sorted linked lists <code>list1</code> and <code>list2</code>.</p>

<p>Merge the two lists into one <strong>sorted</strong> list. The list should be made by splicing together the nodes of the first two lists.</p>

<p>Return <em>the head of the merged linked list</em>.</p>


<p><strong class="example">Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/10/03/merge_ex1.jpg" style="width: 662px; height: 302px;" />
<pre>
<strong>Input:</strong> list1 = [1,2,4], list2 = [1,3,4]
<strong>Output:</strong> [1,1,2,3,4,4]
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> list1 = [], list2 = []
<strong>Output:</strong> []
</pre>

<p><strong class="example">Example 3:</strong></p>

<pre>
<strong>Input:</strong> list1 = [], list2 = [0]
<strong>Output:</strong> [0]
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in both lists is in the range <code>[0, 50]</code>.</li>
	<li><code>-100 &lt;= Node.val &lt;= 100</code></li>
	<li>Both <code>list1</code> and <code>list2</code> are sorted in <strong>non-decreasing</strong> order.</li>
</ul>


### Code Solution

```python
class Solution:
    def mergeTwoLists(self, list1, list2):
        dummy = ListNode(0)
        
        temp = dummy
        while list1 or list2:
            v1 = float('inf') if not list1 else list1.val
            v2 = float('inf') if not list2 else list2.val
            if v1 > v2:
                temp.next = ListNode(v2)
                list2 = None if not list2 else list2.next
            else:
                temp.next = ListNode(v1)
                list1 = None if not list1 else list1.next
            temp = temp.next
        
        return dummy.next
```
