# [Fizz Buzz](https://leetcode.com/explore/featured/card/top-interview-questions-easy/102/math/743/)

The solution runs in O(n) complexity Computationally and spatially.
___
```python
class Solution(object):
    def fizzBuzz(self, n):
        """
        :type n: int
        :rtype: List[str]
        """
        result_arr = []
        for i in range(1, n+1):
            num = ""
            if i%3 == 0:
                num = "Fizz"
            if i%5 == 0:
                num += "Buzz"
            if not num:
                num = str(i)
            result_arr.append(num)
        return result_arr
        
```
___