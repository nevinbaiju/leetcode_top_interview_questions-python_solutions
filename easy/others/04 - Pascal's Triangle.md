# [Pascal's Triangle](https://leetcode.com/explore/featured/card/top-interview-questions-easy/99/others/601/)

___
```python
class Solution(object):
    def generate(self, numRows):
        """
        :type numRows: int
        :rtype: List[List[int]]
        """
        pascals_triange = []
        for i in range(1, numRows+1):
            current_row = [1] * i
            pascals_triange.append(current_row)
            for i in range(1, len(current_row)-1):
                current_row[i] = previous_row[i-1] + previous_row[i]
            previous_row = current_row
        
        return pascals_triange
```
___