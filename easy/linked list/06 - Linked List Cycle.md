# [Linked List Cycle](https://leetcode.com/explore/featured/card/top-interview-questions-easy/93/linked-list/773/)

The solution runs in linear time and O(1) space.
___
```python
class Solution:
    def hasCycle(self, head: ListNode) -> bool:
        slow_ptr = head
        fast_ptr = head
        while(fast_ptr is not None):
            slow_ptr = slow_ptr.next
            if(fast_ptr.next is not None):
                fast_ptr = fast_ptr.next.next
            else:
                return False
            if(slow_ptr == fast_ptr):
                return True
        return False
```
___