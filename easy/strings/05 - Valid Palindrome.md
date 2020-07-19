# [Valid Palindrome](https://leetcode.com/explore/interview/card/top-interview-questions-easy/127/strings/883/)

The solution was obtained in linear time with another string being allocated. The solution can be further optimized by halting the reverse check in the middle.

```python
class Solution:
    def cleanString(self, s):
        new_str = ""
        for char in s:
            if (char.isalpha()) or (char.isnumeric()):
                new_str += char
        return new_str.lower()
    
    def isPalindrome(self, s: str) -> bool:
        s = self.cleanString(s)
        for index in range(len(s)):
            if(s[index] != s[len(s)-index-1]):
                return False
        return True
```        