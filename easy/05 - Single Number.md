# [Single Number](https://leetcode.com/explore/interview/card/top-interview-questions-easy/92/array/549/)

The solution to the problem was achieved with a computational complexity of O(n) but the space complexity was O(2n).
___
```
class Solution:
    def singleNumber(self, nums) -> int:
        buffer = {}
        ans = None
        for item in nums:
            try:
                if (buffer[item]):
                    buffer[item] = False
            except KeyError:
                ans = item
                buffer[item] = True
        for item in nums:
            if buffer[item]:
                return item
```
___
Going through the forums, this solution was able to achieve it by optimizing and removing the need for allocating memory for a hash table.

___
```            
class Solution:
    def singleNumber(self, nums) -> int:
        a = 0
        for item in nums:
            a ^= item
        return a
```
___