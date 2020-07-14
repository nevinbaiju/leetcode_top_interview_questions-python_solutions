
# [Rotate Array](https://leetcode.com/explore/interview/card/top-interview-questions-easy/92/array/646/)
___
```
class Solution:
    def rotate(self, nums: list, k: int) -> None:
    """
    The solution expects nums to be modified inplace.
    """
        k = k%len(nums)
        first_half = nums[:-k]
        second_half = nums[-k:]
        for index in range(len(second_half)):
            nums[index] = second_half[index]
        for index in range(len(first_half)):
            nums[index+k] = first_half[index]
```
___