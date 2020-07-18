# [First Unique Character in a String](https://leetcode.com/explore/interview/card/top-interview-questions-easy/127/strings/881/)

In order to solve the problem in linear time, a hash map was used to count the number of occurances.
___
```
class Solution:
    def getCounts(self, s: str) -> dict:
        hash_map = {}
        for item in s:
            try:
                if(hash_map[item]):
                    hash_map[item] += 1
            except KeyError:
                hash_map[item] = 1
        return hash_map
    def firstUniqChar(self, s: str) -> int:
        hash_map = self.getCounts(s)
        for index in range(len(s)):
            if hash_map[s[index]] == 1:
                return index
        return -1
```
___