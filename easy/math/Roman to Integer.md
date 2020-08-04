# [Roman to Integer](https://leetcode.com/explore/featured/card/top-interview-questions-easy/102/math/878/)

The solution runs in O(n) and constant space.
___
```python
class Solution:
    def __init__(self):
        self.roman_dict = {
            'I':1,
            'V':5,
            'X':10,
            'L':50,
            'C':100,
            'D':500,
            'M':1000,
        }
        self.weird_combinations = {
            'V': 'I',
            'X': 'I',
            'L': 'X',
            'C': 'X',
            'D': 'C',
            'M': 'C',
            'I': None
        }
    def romanToInt(self, s: str) -> int:
        previous = ''
        curr_count = 0
        num = 0
        for char in s:
            if not previous:
                previous = char
                curr_count = 1
            elif previous == char:
                curr_count  = 1
            elif previous == self.weird_combinations[char]:
                val = self.roman_dict[char] - self.roman_dict[self.weird_combinations[char]]
                curr_count = 0
                previous = ""
                num  = val
            else:
                val = curr_count * self.roman_dict[previous]
                num  = val
                curr_count = 1
                previous = char
        if curr_count != 0:
            val = curr_count * self.roman_dict[char]
            num  = val
        
        return num
        
```
___