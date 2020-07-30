# [Merge Sorted Array](https://leetcode.com/explore/featured/card/top-interview-questions-easy/96/sorting-and-searching/587/)

The solution runs at O(m)(Computationally and space wise) where m is the size of the tree.
___
```python
class Solution(object):
    def merge(self, nums1, m, nums2, n):
        """
        :type nums1: List[int]
        :type m: int
        :type nums2: List[int]
        :type n: int
        :rtype: None Do not return anything, modify nums1 in-place instead.
        """
        temp_nums1 = nums1[:m]
        print(temp_nums1, nums2)
        i = 0
        j = 0
        k = 0
        while((i < m) and (j < n)):
            if(temp_nums1[i] <= nums2[j]):
                nums1[k] = temp_nums1[i]
                i += 1
            else:
                nums1[k] = nums2[j]
                j += 1
            print(k, nums1)
            k += 1
        while(i < m):
            nums1[k] = temp_nums1[i]
            k += 1
            i += 1
        while(j < n):
            nums1[k] = nums2[j]
            j += 1
            k += 1
        
```
___