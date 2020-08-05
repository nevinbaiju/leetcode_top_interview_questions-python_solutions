# [Power of Three](https://leetcode.com/explore/featured/card/top-interview-questions-easy/102/math/745/)

I am only submitting this solution because log was having precision problems on their system. log(243) in my system was 5 but in theirs its 4.999 for some reason. The computation and space is in O(1).
___
```python
import math
class Solution(object):
    def isPowerOfThree(self, n):
        """
        :type n: int
        :rtype: bool
        """
        arr = [3**x for x in range(21)]
        if n in arr:
            return True
        else:
            return False
        
```
___