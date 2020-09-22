# [Majority Element](https://leetcode.com/explore/interview/card/top-interview-questions-medium/114/others/824/)

O(n) Time complexity linear searching with hashing.

```python
import math

class Solution:
    def majorityElement(self, nums) -> int:
        majority_count = math.ceil(len(nums)/2)
        count_dict = {}
        for item in nums:
            item_count = count_dict.get(item, 0) + 1
            if item_count >= majority_count:
                return item
            else:
                count_dict[item] = item_count
```
