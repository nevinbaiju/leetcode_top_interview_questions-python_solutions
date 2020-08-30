# [Number of Islands](https://leetcode.com/explore/interview/card/top-interview-questions-medium/108/trees-and-graphs/792/)

Iterative approach.
___
```python
class Solution(object):
    def inorderTraversal(self, root):
        """
        :type root: TreeNode
        :rtype: List[int]
        """
        # Set current to root of binary tree 
        current = root  
        stack = []
        result = []
        done = 0 

        while True: 
            if current is not None:
                stack.append(current) 
                current = current.left  
            elif(stack): 
                current = stack.pop() 
                result.append(current.val)
                current = current.right 
            else: 
                break

        return result
```
___