# [Move Zeroes](https://leetcode.com/explore/interview/card/top-interview-questions-easy/92/array/567)

The solution expects the method to achieve it in-place. The solution runs at a worst case complexity of O(n).

```
def moveZeroes(nums):
    num_zeroes = 0
    index = 0
    while(index < len(nums)):
        if nums[index] == 0:
            num_zeroes += 1
            del nums[index]
            continue
        index += 1
    for i in range(num_zeroes):
        nums.append(0)
```