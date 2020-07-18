# [Contains Duplicate](https://leetcode.com/explore/interview/card/top-interview-questions-easy/92/array/578/)

The solution to the problem was achieved with a complety of O(n) in terms of computation and O(1) in terms of space.

___

```
class Solution:
    def containsDuplicate(self, nums: list) -> bool:
        unique = {}
        for item in nums:
            try:
                if(unique[item]):
                    return True
            except KeyError:
                unique[item] = True
        return False
```
___