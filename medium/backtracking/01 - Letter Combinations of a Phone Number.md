# [Letter Combinations of a Phone Number](https://leetcode.com/explore/interview/card/top-interview-questions-medium/109/backtracking/793/)

The worstcase runtime complexity is O(4^nlog(n)) and space is O(4^n) for storing the output.

```python
class Solution:
    def __init__(self):
        self.num_mapping = {
            '1': [],
            '2': ['a', 'b', 'c'],
            '3': ['d', 'e', 'f'],
            '4': ['g', 'h', 'i'],
            '5': ['j', 'k', 'l'],
            '6': ['m', 'n', 'o',],
            '7': ['p', 'q', 'r', 's'],
            '8': ['t', 'u', 'v',],
            '9': ['w', 'x', 'y', 'z'],
        }
    def merge(self, list_a, list_b):
        result_arr = []
        for item_a in list_a:
            for item_b in list_b:
                result_arr.append(item_a + item_b)
        return [result_arr]
    def find_combinations(self, arr, l , r):
        if len(arr[l:r]) > 1:
            mid = (l+r)//2
            arr_a = self.find_combinations(arr, l, mid)[0]
            arr_b = self.find_combinations(arr, mid, r)[0]
            return self.merge(arr_a, arr_b)
        else:
            return arr[l:r]
    def letterCombinations(self, digits: str):
        if not digits:
            return []
        req_lists = []
        for digit in digits:
            req_lists.append(self.num_mapping[digit])
        return self.find_combinations(req_lists, 0, len(req_lists))[0]
        
        
```
