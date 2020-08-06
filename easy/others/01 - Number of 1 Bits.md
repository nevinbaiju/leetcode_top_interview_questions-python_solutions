# [Number of 1 Bits](https://leetcode.com/explore/interview/card/top-interview-questions-easy/99/others/565/)

The solution completes in constant space but log(n) in worst case, but since the test cases are upper bounded by 32 bit numbers, that is as bad as it gets computationally.
___
```python
class Solution(object):
    def hammingWeight(self, n):
        """
        :type n: int
        :rtype: int
        """
        print(n)
        num_ones = 0
        while(n >= 1):
            if(n % 2):
                num_ones += 1
            n //= 2
        return num_ones
```
___