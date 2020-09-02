# [Intersection of Two Linked Lists](https://leetcode.com/explore/interview/card/top-interview-questions-medium/107/linked-list/785/)

This original solution takes O(n+m) space and time complexity.

```python
class Solution:
    def getIntersectionNode(self, headA: ListNode, headB: ListNode) -> ListNode:
        stack_a = []
        stack_b = []
        
        current = headA
        while current:
            stack_a.append(current)
            current = current.next
        
        current = headB
        while current:
            stack_b.append(current)
            current = current.next
        
        last_common = None
        while(stack_a and stack_b):
            a = stack_a.pop()
            b = stack_b.pop()
            if a == b:
                last_common = a
            else:
                break
        
        return last_common
        
```

Solution with constant space:

```python

def getIntersectionNode(self, headA, headB):
    if headA and headB:
        A, B = headA, headB
        while A!=B:
            A = A.next if A else headB
            B = B.next if B else headA
        return A
```
