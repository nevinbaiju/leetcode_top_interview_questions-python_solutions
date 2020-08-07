# [Hamming Distance](https://leetcode.com/explore/featured/card/top-interview-questions-easy/99/others/762/)

The solution runs in O(n) Where n is the number of bits. And memory is constant.
___
```python
class Solution(object):
    def hammingDistance(self, x, y):
        """
        :type x: int
        :type y: int
        :rtype: int
        """
        hamming_dist = 0
        while(x or y):
            if(x):
                bit_x = x%2
                x //= 2
            else:
                bit_x = 0
            if(y):
                bit_y = y%2
                y //= 2
            else:
                bit_y = 0
            hamming_dist += bit_x ^ bit_y
        
        return hamming_dist
```
___