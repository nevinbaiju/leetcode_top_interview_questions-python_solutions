# [Binary Tree Level Order Traversal](https://leetcode.com/explore/featured/card/top-interview-questions-easy/94/trees/628/)

The solution runs at O(m)(Computationally and space wise) where m is the size of the tree.
___
```python
class Solution:
    def levelOrder(self, root: TreeNode) -> List[List[int]]:
        if root is None:
            return []
        level_elements = [root]
        element_levels = []
        while(level_elements):
            next_level_elements = []
            current_level_elements = []
            for node in level_elements:
                left = node.left
                right = node.right
                if(left):
                    next_level_elements.append(left)
                if(right):
                    next_level_elements.append(right)
                current_level_elements.append(node.val)
            level_elements = next_level_elements
            element_levels.append(current_level_elements)
        return element_levels
        
```
___