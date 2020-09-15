# [Excel Sheet Column Number](https://leetcode.com/explore/interview/card/top-interview-questions-medium/113/math/817)
___
```python
class Solution(object):
    def __init__(self):
        self.alpha_vals = {'A' :1,
                            'B' :2,
                            'C' :3,
                            'D' :4,
                            'E' :5,
                            'F' :6,
                            'G' :7,
                            'H' :8,
                            'I' :9,
                            'J' :10,
                            'K' :11,
                            'L' :12,
                            'M' :13,
                            'N' :14,
                            'O' :15,
                            'P' :16,
                            'Q' :17,
                            'R' :18,
                            'S' :19,
                            'T' :20,
                            'U' :21,
                            'V' :22,
                            'W' :23,
                            'X' :24,
                            'Y' :25,
                            'Z' :26,}
    def titleToNumber(self, s):
        """
        :type s: str
        :rtype: int
        """
        col_num = 0
        power = 0
        for i in range(len(s)-1, -1, -1):
            print(i, s[i])
            col_num += self.alpha_vals[s[i]] * (26**power)
            power += 1
        
        return col_num
```
___