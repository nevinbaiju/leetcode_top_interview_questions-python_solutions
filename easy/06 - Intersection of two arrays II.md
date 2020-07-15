[Intersection of Two Arrays II](https://leetcode.com/explore/interview/card/top-interview-questions-easy/92/array/674/)

The solution has a worst case computational complexity of O(n x m).

___
```
class Solution:
    def intersection(self, a, b):
        intersection = []
        for item in a:
            for i in range(len(b)):
                print(item)
                if(item == b[i]):
                    intersection.append(item)
                    del b[i]
                    break
        return intersection
    
    def intersect(self, nums1, nums2):
        if len(nums1) < len(nums2):
            return self.intersection(nums1, nums2)
        else:
            return self.intersection(nums2, nums1)
```
___