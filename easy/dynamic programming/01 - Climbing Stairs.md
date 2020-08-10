# [Climbing Stairs](https://leetcode.com/explore/interview/card/top-interview-questions-easy/97/dynamic-programming/569/discuss/25299/Basically-it's-a-fibonacci.)

This is a problem that had me confused for a while. All thanks to [this post](https://leetcode.com/explore/interview/card/top-interview-questions-easy/97/dynamic-programming/569/discuss/25299/Basically-it's-a-fibonacci.) for understanding the concept.

___
```python
class Solution(object):
    def climbStairs(self, n):
        """
        :type n: int
        :rtype: int
        """
        solutions = {0: 0, 1: 1, 2: 2}
        for i in range(3, n+1):
            one_step_before = solutions[i - 1]
            two_step_before = solutions[i - 2]
            solutions[i] = one_step_before + two_step_before
        
        return solutions[n]
```
___