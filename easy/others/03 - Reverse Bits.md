# [Reverse Bits](https://leetcode.com/explore/featured/card/top-interview-questions-easy/99/others/648/)

The solution has constant runtime and space.
___
```python
class Solution:
    # @param n, an integer
    # @return an integer
    def reverseBits(self, n):
        reversed_num = 0
        for i in range(31, -1, -1):
            reversed_num += (n%2) * (2**i)
            n //= 2
            
        return reversed_num
```
___