# [Maximum Depth of Binary Tree](https://leetcode.com/explore/featured/card/top-interview-questions-easy/94/trees/555/)

The solution runs at O(m)(Computationally and space wise) where m is the size of the tree.
___
```python
# Definition for a binary tree node.
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right
        
class Solution:
    
    def __init__(self):
        self.current_height = 0
        self.max_height = 0
        
    def modifiedInOrder(self, node, depth):
        depth_list = []
        if node:
            depth = depth+1
            depth_list.append(depth)
            depth_list = depth_list + self.modifiedInOrder(node.left, depth)
            depth_list = depth_list + self.modifiedInOrder(node.right, depth)
        return depth_list
    
    def maxDepth(self, root: TreeNode) -> int:
        depth_list = self.modifiedInOrder(root, 0)
        if depth_list:
            return max(depth_list)
        else:
            return 0
```
___