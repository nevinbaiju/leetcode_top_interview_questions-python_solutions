# [Rotate Image](https://leetcode.com/explore/interview/card/top-interview-questions-easy/92/array/770/)

The solution was achieved using simple matrix indexing. A buffer was created to store the matrix while rotation is performed. The Solution is achieved with a computational complexity of O(n^2). And a space complexity of O(n).

```
import copy

class Solution:
    def rotate(self, matrix) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        """
        buffer = copy.deepcopy(matrix)
        height = len(matrix)
        width = len(matrix[0])
        for row in range(height):
            for column in range(width):
                matrix[column][height-1-row] = buffer[row][column]
```          