# [Count Primes](https://leetcode.com/explore/featured/card/top-interview-questions-easy/102/math/744/)

It uses a counting approach to eliminate multiples of a prime number. Since analysing its complexity was beyond the technology of my time. xP Help me in the issues if you can figure this out.
For getting a pythonic solution, I used dictionary to speed up faster rather than a list. In C, i would've used a simple number as index based hashing. The space complexity is O(n)
___
```python
class Solution(object):
    def countPrimes(self, n):
        """
        :type n: int
        :rtype: int
        """
        num_run = 0
        list_primes = {}
        for i in range(2, n):
            list_primes[i] = False
        for item in range(2, n):
            if(list_primes[item]):
                continue
            start_num = item * item
            for i in range(start_num, n, item):
                num_run +=1
                list_primes[i] = True
        num_primes = 0
        for i in range(2, n):
            if(list_primes[i]):
                continue
            else:
                 num_primes += 1
        return num_primes
        
```
___