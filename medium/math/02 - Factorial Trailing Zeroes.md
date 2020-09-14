# [Factorial Trailing Zeroes](https://leetcode.com/explore/interview/card/top-interview-questions-medium/113/math/816)
___
```python
class Solution(object):
    def trailingZeroes(self, n):
        """
        :type n: int
        :rtype: int
        """
        return 0 if n == 0 else n / 5 + self.trailingZeroes(n / 5)
```