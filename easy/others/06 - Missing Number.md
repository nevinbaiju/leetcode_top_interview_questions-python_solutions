# [Missing Number](https://leetcode.com/explore/featured/card/top-interview-questions-easy/99/others/722/)

The solution runs in O(n) time complexity and space is O(n-1).

___
```python
class Solution(object):
    def missingNumber(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        hash_table = {}
        for item in nums:
            hash_table[item] = True
        for i in range(len(nums)+1):
            try:
                hash_table[i]
            except KeyError:
                return i
```
___