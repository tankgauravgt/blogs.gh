---
title: "0002: Add Two Numbers"
tags:
  - LinkedList
  - Math
  - Recursion
---
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
