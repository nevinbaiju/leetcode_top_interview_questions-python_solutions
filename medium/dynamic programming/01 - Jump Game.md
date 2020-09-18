# [Number of Islands](https://leetcode.com/explore/interview/card/top-interview-questions-medium/108/trees-and-graphs/792/discuss/56340/Python-Simple-DFS-Solution)

Brute Force
```python
class Solution:
    def canJump(self, nums) -> bool:
        if not nums:
            return True
        max_jumps = nums[0]
        jump = 1
        while (jump <= max_jumps) and (jump <= len(nums)):
            print(nums[jump:], jump)
            if self.canJump(nums[jump:]):
                return True
            jump += 1
        return False
```

Cached solution
```python
 class Solution:
    def checkSafeReachable(self, nums, idx):
        max_jumps = nums[idx]
        for jump_index in range(min(len(nums)-1, idx+max_jumps), idx, -1):
#         for jump_index in range(idx+1, min(len(nums), idx+max_jumps)):
#         for jump in range(1, max_jumps+1):
#             jump_index = idx+jump
            if self.memo.get(jump_index, False):
                return True
        else:
            False
    def canJump(self, nums) -> bool:
        self.memo = {len(nums)-1: True}
        for i in range(len(nums)-1, -1, -1):
            if self.memo.get(i, False):
                self.memo[i] = True
            elif self.checkSafeReachable(nums, i):
                self.memo[i] = True
            else:
                self.memo[i] = False
#         print(self.memo)
        return self.memo[0]
```

Copied Solution xP
```python
class Solution:
    def canJump(self, nums):
        max_reach, n = 0, len(nums)
        for i, x in enumerate(nums):
            if max_reach < i: return False
            if max_reach >= n - 1: return True
            max_reach = max(max_reach, i + x)
```
