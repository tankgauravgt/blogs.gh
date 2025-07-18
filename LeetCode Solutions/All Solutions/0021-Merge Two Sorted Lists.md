---
title: "0021: Merge Two Sorted Lists"
---
```python
class Solution:
    def mergeTwoLists(self, list1, list2):
        def rev(head):
            prev = None
            curr = head
            while curr:
                temp = curr.next
                curr.next = prev
                prev = curr
                curr = temp
            return prev
        result = None
        while list1 and list2:
            if list1.val < list2.val:
                result = ListNode(list1.val, result)
                list1 = list1.next
                continue
            result = ListNode(list2.val, result)
            list2 = list2.next
        while list1:
            result = ListNode(list1.val, result)
            list1 = list1.next
        while list2:
            result = ListNode(list2.val, result)
            list2 = list2.next
        return rev(result)
```
