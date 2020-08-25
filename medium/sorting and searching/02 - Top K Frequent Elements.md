# [Top K Frequent Elements](https://leetcode.com/explore/interview/card/top-interview-questions-medium/110/sorting-and-searching/799/)

O(n) time and space complexity.

```python
class Solution:
    def topKFrequent(self, nums, k):
        count_dict = {}
        for item in nums:
            count_dict[item] = count_dict.get(item, 0) + 1
        
        count_vals = {}
        for key in count_dict.keys():
            count = count_dict[key]
            count_vals[count] = count_vals.get(count, []) + [key]
            
        result = []
        for count in range(len(nums), -1, -1):
            element = count_vals.get(count, None)
            if element is not None:
                result = result + element
                if len(result) == k:
                    return result
        return result
```
