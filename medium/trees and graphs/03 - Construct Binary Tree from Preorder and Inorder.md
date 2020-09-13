# [Construct Binary Tree from Preorder and Inorder Traversal](https://leetcode.com/explore/interview/card/top-interview-questions-medium/108/trees-and-graphs/788/)
___
```python
class Solution:
    def buildTree(self, preorder, inorder):
            if inorder:
                # print(preorder, inorder)
                popped = preorder.pop(0)
                ind = inorder.index(popped)
                # print(popped)
                root = TreeNode(inorder[ind])
                root.left = self.buildTree(preorder, inorder[0:ind])
                root.right = self.buildTree(preorder, inorder[ind+1:])
                return root
```
___