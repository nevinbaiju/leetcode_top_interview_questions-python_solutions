# [Remove Nth Node From End of List](https://leetcode.com/explore/featured/card/top-interview-questions-easy/93/linked-list/603/)

To solve the problem in linear time, a list was used to store the nodes and then it was deleted using the delete function of the previous problem excluding some boundary conditions. This has a worst case time complexity and space complexity of O(n). **An optimization to this would be to check boundary condition 1 (if deleting the first element) initially before while loop and then that would be done in constant time.**

```python
# Definition for singly-linked list.
class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next
        
class Solution:
    def deleteNode(self, node):
        node.val = node.next.val
        node.next = node.next.next
        
    def removeNthFromEnd(self, head: ListNode, n: int) -> ListNode:
        current = head
        node_list = [current]
        while current.next is not None:
            node_list.append(current.next)
            current = current.next
        if n == len(node_list):
            head = head.next
            return head
        elif n == 1:
            node_list[-2].next = None
        else:
            self.deleteNode(node_list[len(node_list)-n])
            
        return head
```