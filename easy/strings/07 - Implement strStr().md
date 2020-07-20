# [Implement strStr()](https://leetcode.com/explore/interview/card/top-interview-questions-easy/127/strings/885/)

The solution gets completed in linear time. We are using a dict object to store the needle which acts as a hash for easy comparison.

```python
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        if(len(needle) > len(haystack)):
            return -1
        elif(haystack == ""):
            return 0
        needle_hash = {needle: True}
        for i in range(len(haystack)-len(needle)+1):
            try:
                if(needle_hash[haystack[i:i+len(needle)]]):
                    return i
            except KeyError:
                continue
        return -1
```        