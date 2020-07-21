# [Count and Say](https://leetcode.com/explore/interview/card/top-interview-questions-easy/127/strings/886/)

Here the count function generates the next number in the sequence. Eventhough, it runs on linear time, when we are generating the number in sequence, it runs on exponential time. So a better limited way to optimize would be to generate and store the answers and then index it properly.

```python
class Solution:
    def count(self, num: str):
        current = num[0]
        count = 1
        countStr = ""
        for index in range(1, len(num)):
            if(num[index] == current):
                count += 1
            else:
                countStr += f"{count}{current}"
                count = 1
                current = num[index]
        countStr += f"{count}{current}"

        return countStr
    
    def countAndSay(self, n: int) -> str:
        num = "1"
        for i in range(1, n):
            num = self.count(num)
        return num
```        