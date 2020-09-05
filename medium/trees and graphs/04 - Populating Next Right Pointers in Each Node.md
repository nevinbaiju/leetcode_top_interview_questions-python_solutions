# [Populating Next Right Pointers in Each Node](https://leetcode.com/explore/interview/card/top-interview-questions-medium/108/trees-and-graphs/789/)

computational time complexity if O(n) and space is O(1) if we ignore the stack used for storing the level nodes.
___
```python
class Solution(object):
    def connect(self, root):
        """
        :type root: Node
        :rtype: Node
        """
        if not root:
            return None
        node_stack = [root]
        prev = None
        while(True):
            next_stack = []
            while node_stack:
                current = node_stack.pop(0)
                if prev:
                    prev.next = current
                if current.left:
                    next_stack.append(current.left)
                if current.right:
                    next_stack.append(current.right)
                prev = current
            prev.next = None
            prev = None
            node_stack = next_stack
            if not node_stack:
                break
        return root
```
___