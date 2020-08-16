# [Longest Substring Without Repeating Characters](https://leetcode.com/explore/interview/card/top-interview-questions-medium/103/array-and-strings/779)

Rage quit plagiarised code from [here](https://leetcode.com/explore/interview/card/top-interview-questions-medium/103/array-and-strings/779/discuss/1731/A-Python-solution-85ms-O(n)).
___
```python
class Solution:
    def lengthOfLongestSubstring(self, s):
        start = maxLength = 0
        usedChar = {}
        
        for i in range(len(s)):
            if s[i] in usedChar and start <= usedChar[s[i]]:
                start = usedChar[s[i]] + 1
            else:
                maxLength = max(maxLength, i - start + 1)

            usedChar[s[i]] = i

        return maxLength
```
___