[Reverse String](https://leetcode.com/explore/interview/card/top-interview-questions-easy/127/strings/879/)

The solution has a worst case complexity of O(n) for space and computation.

___

```
class Solution:
    def reverseString(self, s):
        buffer = s.copy()
        for i in range(len(s)):
            s[i] = buffer[len(s)-i-1]
```        
___