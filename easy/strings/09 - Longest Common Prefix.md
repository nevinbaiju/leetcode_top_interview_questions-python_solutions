# [Longest Common Prefix](https://leetcode.com/explore/featured/card/top-interview-questions-easy/127/strings/887/)

The solution to the problem runs in o(nxm). (n the length of the first string and m the length of the array.) Scope for improvement involves selecting the smallest string to iterate over its prefixes.

___
```python
class Solution:
    def checkSubString(self, substring, string):
        if(substring) == string[0:len(substring)]:
            return True
        else:
            return False
    def longestCommonPrefix(self, strs) -> str:
        if not strs:
            return ""
        first = strs[0]
        best_substring = ""
        for i in range(1, len(first)+1):
            substring = first[0:i]
            streak = True
            for strng in strs[1:]:
                if not(self.checkSubString(substring, strng)):
                    streak = False
                    break
            if streak:
                best_substring = substring
        return best_substring
```
___