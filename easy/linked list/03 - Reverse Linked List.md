# [Reverse Linked List](https://leetcode.com/explore/featured/card/top-interview-questions-easy/93/linked-list/560/)

The problem runs in linear time. In all cases it takes O(n) and space complexity is constant. 
___
```python
# Definition for singly-linked list.
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next
        
class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
        # Handling empty and single element LL
        if head is None:
            return head
        elif head.next is None:
            return head
        # Reversal Logic
        previous = head
        current = head.next
        previous.next = None
        while(current.next is not None):
            next_node = current.next
            current.next = previous
            previous = current
            current = next_node
        
        current.next = previous
        head = current
        
        return head
```
___