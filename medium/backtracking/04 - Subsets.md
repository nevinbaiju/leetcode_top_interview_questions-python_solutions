# [Subsets](https://leetcode.com/explore/interview/card/top-interview-questions-medium/109/backtracking/796/)

This is a top down approach from the modified permutations solution.

```python
class Solution:
    def subsets(self, nums):
        result = []
        self.dfs(nums, [], result)
        
        return result
    
    def dfs(self, nums, path, result):
        if not nums:
            if path not in result:
                result.append(path)
        else:
            for i in range(len(nums)):
                self.dfs(nums[i+1:], path+[nums[i]], result)
                self.dfs(nums[i+1:], path, result)
```
