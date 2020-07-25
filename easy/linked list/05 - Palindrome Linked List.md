# [Palindrome Linked List](https://leetcode.com/explore/featured/card/top-interview-questions-easy/93/linked-list/772/)

The solution runs in O(n+m) time and constant space.
___
```python
# Definition for singly-linked list.
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next
        
class Solution:
    def isPalindrome(self, head: ListNode) -> bool:
        stack = []
        current = head
        while(current is not None):
            stack.append(current.val)
            current = current.next
        current = head
        while(current is not None):
            if(stack[-1] == current.val):
                stack.pop()
                current = current.next
            else:
                return False
        return True
        
```
___