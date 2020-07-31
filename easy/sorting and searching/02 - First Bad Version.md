# [First Bad Version](https://leetcode.com/explore/featured/card/top-interview-questions-easy/96/sorting-and-searching/774/)

The solution runs in O(log(n)) complexity and constant space complexity. This is a modification of binary search.
___
```python
class Solution(object):
    def firstBadVersion(self, n):
        """
        :type n: int
        :rtype: int
        """
        first_version = 1
        final_version = n
        while(True):
            middle_version = (first_version + final_version) // 2
            if ((isBadVersion(middle_version)) and not (isBadVersion(middle_version-1))):
                return middle_version
            elif(isBadVersion(middle_version)):
                final_version = middle_version - 1
            else:
                first_version = middle_version + 1
        
```
___