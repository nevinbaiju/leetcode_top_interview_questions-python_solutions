# [Binary Tree Zigzag Level Order Traversal](https://leetcode.com/submissions/detail/389352439/?from=/explore/interview/card/top-interview-questions-medium/108/trees-and-graphs/787/)

OC
___
```python
class Solution(object):
    def zigzagLevelOrder(self, root):
        """
        :type root: TreeNode
        :rtype: List[List[int]]
        """
        if not root:
            return []
        current_level = [root]
        result = []
        odd = False
        while True:
            print(current_level)
            next_level = []
            current_result = []
            while current_level:
                if odd:
                    print("Reverse")
                    current = current_level.pop()
                    print(current.val)
                    current_result.append(current.val)
                    if current.right:
                        next_level.insert(0, current.right)
                    if current.left:
                        next_level.insert(0, current.left)
                else:
                    print("Correct")
                    current = current_level.pop(0)
                    print(current.val)
                    current_result.append(current.val)
                    if current.left:
                        next_level.append(current.left)
                    if current.right:
                        next_level.append(current.right)
            
            odd = not odd
                    
            result.append(current_result)
            if next_level:
                current_level = next_level
            else:
                break
        
        return result
```
___