# [Sort Colors](https://leetcode.com/explore/interview/card/top-interview-questions-medium/110/sorting-and-searching/798)

The most obvious way is to use sorting. However it can't be better than O(nlog(n)).
Counting sort will use constant space as there are only 3 elements but would require 2 passes.
[This approach](https://leetcode.com/explore/interview/card/top-interview-questions-medium/110/sorting-and-searching/798/discuss/26481/Python-O(n)-1-pass-in-place-solution-with-explanation) does the job beautifully.

```python
class Solution:
    def sortColors(self, nums):
        red, white, blue = 0, 0, len(nums)-1

        while white <= blue:
            if nums[white] == 0:
                nums[red], nums[white] = nums[white], nums[red]
                white += 1
                red += 1
            elif nums[white] == 1:
                white += 1
            else:
                nums[white], nums[blue] = nums[blue], nums[white]
                blue -= 1
```
