# [Reverse Integer](https://leetcode.com/explore/interview/card/top-interview-questions-easy/127/strings/880/)


___
```
class Solution:
    def reverse(self, x: int) -> int:
        if x < 0:
            sign = -1
            x = -x
        else:
            sign = 1
        result = 0
        while(x > 0):
            result = ((result*10) + (x % 10))
            x = x//10
        result = result * sign
        if ((result > 2147483641) | (result < -2147483641)):
            return 0
        else:
            return result
```            
___        