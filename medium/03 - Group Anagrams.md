# [Group Anagrams](https://leetcode.com/explore/interview/card/top-interview-questions-medium/103/array-and-strings/778)

___
```python
class Solution(object):
    def groupAnagrams(self, strs):
        """
        :type strs: List[str]
        :rtype: List[List[str]]
        """
        char_hash = {}
        for word in strs:
            key = "".join(sorted(word))
            char_hash[key] = char_hash.get(key, []) + [word]
        return char_hash.values()
```
___