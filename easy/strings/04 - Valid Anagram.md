# [Valid Anagram](https://leetcode.com/explore/interview/card/top-interview-questions-easy/127/strings/882/)

The solution was obtained using linear computational time with O(n) in the worst case. Two dictionaries are created, so they will form O(2n) in terms of space but is also linear.

___
```python
class Solution:
    def getHashMap(self, s: str) -> dict:
        hash_map = {}
        for item in s:
            try:
                if(hash_map[item]):
                    hash_map[item] += 1
            except KeyError:
                hash_map[item] = 1
        return hash_map
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False
        s_hash_map = self.getHashMap(s)
        t_hash_map = self.getHashMap(t)
        for key in s_hash_map.keys():
            try:
                if s_hash_map[key] == t_hash_map[key]:
                    continue
                else:
                    return False
            except KeyError:
                return False
        return True
```
___