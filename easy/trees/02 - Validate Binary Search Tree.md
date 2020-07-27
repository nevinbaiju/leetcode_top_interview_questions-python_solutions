# [Validate Binary Search Tree](https://leetcode.com/explore/featured/card/top-interview-questions-easy/94/trees/625/)

The solution runs at O(m)(Computationally and space wise) where m is the size of the tree.
___
```python
# Definition for a binary tree node.
class Solution:
    def inorderTraversal(self, node):
        res = []
        if node:
            res = self.inorderTraversal(node.left)
            res.append(node.val)
            res = res + self.inorderTraversal(node.right)
        return res
    def isValidBST(self, root: TreeNode) -> bool:
        traversed = self.inorderTraversal(root)
        for i in range(1, len(traversed)):
            if (traversed[i] <= traversed[i-1]):
                return False
        return True
```
___