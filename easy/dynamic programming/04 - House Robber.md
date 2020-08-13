# [Maximum Subarray](https://leetcode.com/explore/interview/card/top-interview-questions-easy/97/dynamic-programming/566/)

A beautiful explanation of it is provided [here](https://leetcode.com/explore/interview/card/top-interview-questions-easy/97/dynamic-programming/576/discuss/156523/From-good-to-great.-How-to-approach-most-of-DP-problems.).
This solution solves it in O(n) time. To solve this in constant space, a further optimization is given in the thread.

___
```python
class Solution(object):
    def __init__(self):
        self.memo = {}
    def rob(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        if not(nums):
            return 0;
        memo = {}
        memo[0] = 0;
        memo[1] = nums[0];
        for i in range(1, len(nums)):
            memo[i+1] = max(memo[i], memo[i-1]+nums[i])
        return memo[len(nums)]
```
___