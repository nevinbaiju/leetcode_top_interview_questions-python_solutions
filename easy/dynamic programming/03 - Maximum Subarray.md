# [Maximum Subarray](https://leetcode.com/explore/interview/card/top-interview-questions-easy/97/dynamic-programming/566/)

This problem is solved using Kadane's algorithm. A beautiful explanation of it is provided [here](https://leetcode.com/explore/interview/card/top-interview-questions-easy/97/dynamic-programming/566/).
This solution solves it in O(n) time.

___
```python
class Solution(object):
    def maxSubArray(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        max_sum = -2**31
        curr_sum = max_sum
        for item in nums:
            curr_sum = max(item, curr_sum+item)
            max_sum = max(max_sum, curr_sum)
        return max_sum
```
___