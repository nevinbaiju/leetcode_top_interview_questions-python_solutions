# [Unique Paths](https://leetcode.com/explore/interview/card/top-interview-questions-medium/111/dynamic-programming/808)
___
```python
class Solution:
    # @return an integer
    def uniquePaths(self, m, n):
        aux = [[1 for x in range(n)] for x in range(m)]
        print(aux)
        for i in range(1, m):
            for j in range(1, n):
                aux[i][j] = aux[i][j-1]+aux[i-1][j]
        return aux[-1][-1]
```
___