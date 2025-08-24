---
title: "0002: Add Two Numbers"
tags:
  - LinkedList
  - Math
  - Recursion
---
### Problem Statement

<p>You are given two <strong>non-empty</strong> linked lists representing two non-negative integers. The digits are stored in <strong>reverse order</strong>, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.</p>

<p>You may assume the two numbers do not contain any leading zero, except the number 0 itself.</p>


<p><strong class="example">Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/10/02/addtwonumber1.jpg" style="width: 483px; height: 342px;" />
<pre>
<strong>Input:</strong> l1 = [2,4,3], l2 = [5,6,4]
<strong>Output:</strong> [7,0,8]
<strong>Explanation:</strong> 342 + 465 = 807.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> l1 = [0], l2 = [0]
<strong>Output:</strong> [0]
</pre>

<p><strong class="example">Example 3:</strong></p>

<pre>
<strong>Input:</strong> l1 = [9,9,9,9,9,9,9], l2 = [9,9,9,9]
<strong>Output:</strong> [8,9,9,9,0,0,0,1]
</pre>


<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in each linked list is in the range <code>[1, 100]</code>.</li>
	<li><code>0 &lt;= Node.val &lt;= 9</code></li>
	<li>It is guaranteed that the list represents a number that does not have leading zeros.</li>
</ul>


### Code Solution

```python
class Solution:
    def addTwoNumbers(self, l1, l2):
    
        result = temp = ListNode(-1, None)
        
        carry = 0
        while l1 or l2:
        
            n1 = 0 if not l1 else l1.val
            n2 = 0 if not l2 else l2.val
            
            total = n1 + n2 + carry
            carry = total // 10
            total = total % 10
            
            temp.next = ListNode(total)
            temp = temp.next
            
            l1 = None if not l1 else l1.next
            l2 = None if not l2 else l2.next
        
        if carry:
            temp.next = ListNode(carry)
            temp = temp.next
        
        return result.next
```
