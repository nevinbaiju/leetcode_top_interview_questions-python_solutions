# [Set Matrix Zeroes](https://leetcode.com/explore/interview/card/top-interview-questions-medium/103/array-and-strings/777)

The solution runs in O(mxn) time complexity. However space complexity will be that much in worst case (When everything is zero). There is a lot of scope for improving this, like marking the first position of col and row and then iterating it over, etc.

___
```python
class Solution(object):
    def __init__(self):
        self.zero_pos = {
            'col': [],
            'row': []
        }
    def setZeroes(self, matrix):
        """
        :type matrix: List[List[int]]
        :rtype: None Do not return anything, modify matrix in-place instead.
        """
        for i in range(len(matrix)):
            for j in range(len(matrix[i])):
                if(matrix[i][j] == 0):
                    self.zero_pos['row'].append(i)
                    self.zero_pos['col'].append(j)
        for row in self.zero_pos['row']:
            matrix[row] = [0]*len(matrix[row])
        for col in self.zero_pos['col']:
            for row in range(len(matrix)):
                matrix[row][col] = 0
        return matrix
```
___