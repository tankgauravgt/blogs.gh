---
title: "0021: Merge Two Sorted Lists"
---
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
