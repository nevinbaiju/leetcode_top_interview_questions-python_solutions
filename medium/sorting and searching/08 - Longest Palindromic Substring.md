# [Longest Palindromic Substring](https://leetcode.com/explore/interview/card/top-interview-questions-medium/103/array-and-strings/780/)

Clunky code, sorry. :P

```python
class Solution:
    def getPalindrome1(self, s, index):
        left_index = index-1
        right_index = index+1
        palindrome = s[index]
        while((left_index >= 0) and
              (right_index < self.total_length) and 
              (s[left_index] == s[right_index])):
            palindrome = s[left_index] + palindrome + s[right_index]
            
            left_index -= 1
            right_index += 1
        
        return palindrome
    
    def getPalindrome2(self, s, index):
        left_index = index
        right_index = index+1
        palindrome = ""
        while((left_index >= 0) and
              (right_index < self.total_length) and 
              (s[left_index] == s[right_index])):
            palindrome = s[left_index] + palindrome + s[right_index]
            
            left_index -= 1
            right_index += 1
        
        return palindrome
    
    def longestPalindrome(self, s: str) -> str:
        self.total_length = len(s)
        longest_palindrome = ""
        longest_palindrome_len = 0
        
        for i in range(self.total_length):
            palindrome1 = self.getPalindrome1(s, i)
            palindrome2 = self.getPalindrome2(s, i)
            if len(palindrome1) > len(palindrome2):
                palindrome = palindrome1
            else:
                palindrome = palindrome2
                
            if len(palindrome) > longest_palindrome_len:
                longest_palindrome = palindrome
                longest_palindrome_len = len(palindrome)

        return longest_palindrome
```
