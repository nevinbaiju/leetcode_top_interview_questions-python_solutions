# [Increasing Triplet Subsequence](https://leetcode.com/explore/interview/card/top-interview-questions-medium/103/array-and-strings/781/)

This solution gets complete in O(n) and O(1) time and space complexity respectively. This insightful solution was provided by [this post](https://leetcode.com/explore/interview/card/top-interview-questions-medium/103/array-and-strings/781/discuss/78995/Python-Easy-O(n)-Solution)

```python
class Solution:
    def increasingTriplet(self, nums) -> bool:
        first = float('inf')
        second = float('inf')
        for item in nums:
            if item <= first:
                first = item
            elif item <= second:
                second = item
            else:
                return True
        return False
```
