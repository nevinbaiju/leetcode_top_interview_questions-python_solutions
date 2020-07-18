# [Remove Duplicates from Sorted Array](https://leetcode.com/explore/featured/card/top-interview-questions-easy/92/array/727/)

```
class Solution:
    def removeDuplicates(self, nums):
        if(len(nums) == 0):
            return 0
        length = 1
        for i in range(1, len(nums)):
            if(nums[i] != nums[i-1]):
                nums[length] = nums[i]
                length += 1
        return length
```