# [Valid Parentheses](https://leetcode.com/explore/featured/card/top-interview-questions-easy/99/others/721/)

The solution runs in O(n) time complexity and space is constant.

___
```python
class Solution(object):
    def __init__(self):
        self.pairs = {
            '}': '{',
            ')': '(',
            ']': '[',
        }
        self.opening = ['{', '[', '(']
        
    def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        stack = []
        for char in s:
            if char in self.opening:
                stack.append(char)
            elif stack: 
                if self.pairs[char] == stack[-1]:
                    stack.pop()
                else:
                    return False
            else:
                return False
        if stack:
            return False
        else:
            return True
```
___