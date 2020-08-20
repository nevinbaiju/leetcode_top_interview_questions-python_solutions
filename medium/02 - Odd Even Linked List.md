# [Odd Even Linked List](https://leetcode.com/explore/interview/card/top-interview-questions-medium/107/linked-list/784/)

The solution runs by assigning next to next.next. And finally attaching the tail of the odd element to the second element.
The solution runs in O(n) time and (1) space.

```python
class Solution:
    def oddEvenList(self, head: ListNode) -> ListNode:
        # Base conditions
        if not head:
            return head
        elif not head.next:
            return head
        
        current = head
        odd_tail = None
        odd = True
        even_head = head.next
        while(current.next):
            temp = current.next
            current.next = current.next.next
            if odd:
                if current.next:
                    odd_tail = current.next
                else:
                    odd_tail = current
                odd = False
            else:
                odd = True
            current = temp
        
        odd_tail.next = even_head
            
        return head
```
