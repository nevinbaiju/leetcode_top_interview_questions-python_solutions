# [Search in Rotated Sorted Array](https://leetcode.com/explore/interview/card/top-interview-questions-medium/110/sorting-and-searching/804/discuss/14437/Python-binary-search-solution-O(logn)-48ms)

The most obvious answer.

```python
class Solution:
    def search(self, nums, target: int) -> int:
        for i, item in enumerate(nums):
            if (item == target):
                return i
        return -1
```

A slightly modified binary search solution from [here](https://leetcode.com/explore/interview/card/top-interview-questions-medium/110/sorting-and-searching/804/discuss/14437/Python-binary-search-solution-O(logn)-48ms).

```python
class Solution:
    def search(self, nums, target):
        if not nums:
            return -1

        low, high = 0, len(nums) - 1

        while low <= high:
            mid = (low + high) / 2
            if target == nums[mid]:
                return mid

            if nums[low] <= nums[mid]:
                if nums[low] <= target <= nums[mid]:
                    high = mid - 1
                else:
                    low = mid + 1
            else:
                if nums[mid] <= target <= nums[high]:
                    low = mid + 1
                else:
                    high = mid - 1

        return -1
```
