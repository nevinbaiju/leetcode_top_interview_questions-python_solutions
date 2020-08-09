# [Convert Sorted Array to Binary Search Tree](https://leetcode.com/explore/interview/card/top-interview-questions-easy/94/trees/631/)

Constant time and space. Credits to [this post](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/discuss/777746/easy-python-solution)

___
```python
class Solution:
    def sortedArrayToBST(self, nums):
        return self.helper(nums, 0, len(nums))

    def helper(self, nums, left, right):
        if left == right:
            return None

        mid = (left + right) // 2
        node = TreeNode(nums[mid])
        node.left = self.helper(nums, left, mid)
        node.right = self.helper(nums, mid+1, right)

        return node
```
___