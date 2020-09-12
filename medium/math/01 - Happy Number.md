# [Happy Number](https://leetcode.com/explore/interview/card/top-interview-questions-medium/113/math/815)
___
```python
class Solution(object):
            
    def isHappy(self, n):
        """
        :type n: int
        :rtype: bool
        """
        seen_nums = set()
        while n != 1:
            n = sum([int(x)**2 for x in str(n)])
            if n in seen_nums:
                return False
            else:
                seen_nums.add(n)
        return True
```
___