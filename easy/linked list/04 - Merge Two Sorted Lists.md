# [Merge Two Sorted Lists](https://leetcode.com/explore/featured/card/top-interview-questions-easy/93/linked-list/771/)

The solution runs in O(n+m) time and constant space.
___
```python
# Definition for singly-linked list.
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next
        
class Solution:
    def mergeTwoLists(self, l1: ListNode, l2: ListNode) -> ListNode:
        temp = ListNode()
        result = temp
        while((l1 is not None) and (l2 is not None)):
            if(l1.val <= l2.val):
                result.next = l1
                l1 = l1.next
            else:
                result.next = l2
                l2 = l2.next
            result = result.next
        
        while(l1 is not None):
            result.next = l1
            l1 = l1.next
            result = result.next
        while(l2 is not None):
            result.next = l2
            l2 = l2.next
            result = result.next
        
        return temp.next
```
___