# [Task Scheduler](https://leetcode.com/explore/interview/card/top-interview-questions-medium/114/others/826)

___
```python
class Solution(object):
    def leastInterval(self, tasks, N):
        task_counts = collections.Counter(tasks).values()
        M = max(task_counts)
        Mct = task_counts.count(M)
        return max(len(tasks), (M - 1) * (N + 1) + Mct)

```
___