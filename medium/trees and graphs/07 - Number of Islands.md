# [Number of Islands](https://leetcode.com/explore/interview/card/top-interview-questions-medium/108/trees-and-graphs/792/discuss/56340/Python-Simple-DFS-Solution)

Computationally and memory wise it is O(n\*m).
Scope for memory optimization for storing visited matrix inside grid itself.

```python
class Solution:
    def dfs(self, grid, node):
        dfs_stack = [node]
        while(dfs_stack):
            current_h, current_w = dfs_stack.pop()
            self.visited[current_h][current_w] = True
            if current_w+1 < self.width:
                if grid[current_h][current_w+1] == "1" and not self.visited[current_h][current_w+1]:
                    dfs_stack.append((current_h, current_w+1))
            if current_w-1 > -1:
                if grid[current_h][current_w-1] == "1" and not self.visited[current_h][current_w-1]:
                    dfs_stack.append((current_h, current_w-1))
            if current_h+1 < self.height:
                if grid[current_h+1][current_w] == "1" and not self.visited[current_h+1][current_w]:
                    dfs_stack.append((current_h+1, current_w))
            if current_h-1 > -1:
                if grid[current_h-1][current_w] == "1" and not self.visited[current_h-1][current_w]:
                    dfs_stack.append((current_h-1, current_w))
                    
    def numIslands(self, grid) -> int:
        if not grid:
            return 0
        self.height = len(grid)
        self.width = len(grid[0])
        self.visited = [[False]*self.width for x in range(self.height)]
        num_components = 0
        for i in range(self.height):
            for j in range(self.width):
                if (not (self.visited[i][j])) and (grid[i][j] == "1"):
                    num_components += 1
                    self.dfs(grid, (i, j))
        return num_components
```
