# [Kth Largest Element in an Array](https://leetcode.com/explore/interview/card/top-interview-questions-medium/110/sorting-and-searching/800/discuss/60294/Solution-explained)

There is scope for improvement, however I used the obvious solution of sorting and finding the kth largest element.
___
```python
class Solution(object):
    def findKthLargest(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: int
        """
        nums.sort()
        
        return nums[-k]
```
___