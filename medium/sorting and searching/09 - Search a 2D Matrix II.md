# [Search a 2D Matrix II](https://leetcode.com/explore/interview/card/top-interview-questions-medium/110/sorting-and-searching/806)

This solution completes in $nlog_2(m)$ time complexity and constant space complexity.
The more optimized time complexity would be to search from the top right corner of the array and thereby optimizing to O(n+m).

```python
class Solution:
    def binarySearch(self, arr, x): 
        low = 0
        high = len(arr) - 1
        mid = 0

        while low <= high: 

            mid = (high + low) // 2
            if arr[mid] < x: 
                low = mid + 1
            elif arr[mid] > x: 
                high = mid - 1
            else: 
                return mid 
            
        return -1
    def searchMatrix(self, matrix, target):
        """
        :type matrix: List[List[int]]
        :type target: int
        :rtype: bool
        """
        for row in matrix:
            result = self.binarySearch(row, target)
            if result != -1:
                return True
        return False
```
