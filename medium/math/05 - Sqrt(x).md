# [Sqrt(x)](https://leetcode.com/explore/interview/card/top-interview-questions-medium/113/math/819/discuss/25061/Python-binary-search-solution-(O(lgn)))

___
```python
class Solution(object):
    def mySqrt(self, x):
        l, r = 0, x
        while l <= r:
            mid = l + (r-l)//2
            if mid * mid <= x < (mid+1)*(mid+1):
                return mid
            elif x < mid * mid:
                r = mid - 1
            else:
                l = mid + 1
```
___