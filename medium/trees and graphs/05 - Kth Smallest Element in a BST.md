# [Kth Smallest Element in a BST](https://leetcode.com/explore/interview/card/top-interview-questions-medium/108/trees-and-graphs/790/)

computational time complexity if O(k) and space is O(1).
___
```python
class Solution(object):
    def kthSmallest(self, root, k):
        """
        :type root: TreeNode
        :type k: int
        :rtype: int
        """
        # Set current to root of binary tree 
        current = root  
        stack = [] # initialize stack 
        done = 0
        while True:
            if not k:
                return prev_element
            if current is not None:
                stack.append(current) 
                current = current.left
            elif(stack): 
                current = stack.pop() 
                prev_element = current.val
                k -= 1
                current = current.right
            else:
                break
```
___