# [Permutations](https://leetcode.com/explore/interview/card/top-interview-questions-medium/109/backtracking/795)

A DFS Solution

```python
class Solution:
    def permute(self, nums):
        result = []
        self.dfs(nums, [], result)
        
        return result
    
    def dfs(self, nums, path, result):
        if not nums:
            result.append(path)
        else:
            for i in range(len(nums)):
                self.dfs(nums[:i]+nums[i+1:], path+[nums[i]], result)
```
