# [Symmetric Tree](https://leetcode.com/explore/featured/card/top-interview-questions-easy/94/trees/627/)

The solution runs at O(m)(Computationally and space wise) where m is the size of the tree.
The solution runs by doing a preorder traversal on the left and an inverse pre order traversal on the right from the root node. In every stage, the two pointers are checked and if in any stage there is an inconsistency, it returns false.
___
```python
class Solution:
    def modifiedInOrder(self, root):
        if root is None:
            return True
        current_1 = root.left
        current_2 = root.right
        stack_1 = []
        stack_2 = []
        done = 0 
        while True:
            if (current_1 is not None) and (current_2 is not None):
                if(current_1.val != current_2.val):
                    return False
                stack_1.append(current_1)
                stack_2.append(current_2)
                current_1 = current_1.left  
                current_2 = current_2.right
            elif(current_1 is not None) or (current_2 is not None):
                return False
            elif(stack_1) and (stack_2): 
                current_1 = stack_1.pop()
                current_2 = stack_2.pop()
                print(current_1.val, current_2.val)
                if current_1.val != current_2.val:
                    return False
                current_1 = current_1.right
                current_2 = current_2.left
            elif(stack_1) or (stack_2):
                return False
            else:
                return True
    
    def isSymmetric(self, root: TreeNode) -> bool:
        return self.modifiedInOrder(root)
        
```
___