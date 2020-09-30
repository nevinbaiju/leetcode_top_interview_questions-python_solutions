# [Longest Increasing Subsequence](https://leetcode.com/explore/interview/card/top-interview-questions-medium/111/dynamic-programming/810)

___
```python
class Solution(object):
    def aggLIS(self, curr, nums):
        print(curr)
        if not curr and nums:
            return max(self.aggLIS(nums[:1], nums[1:]),
                        self.aggLIS([], nums[1:]))
        elif not nums:
            return len(curr)
        elif curr[-1] < nums[0]:
            return max(self.aggLIS(curr + nums[:1], nums[1:]),
                       self.aggLIS(curr, nums[1:]))
        else:
            return self.aggLIS(curr, nums[1:])
    def lengthOfLIS(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        return self.aggLIS([], nums)
```
___