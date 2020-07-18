# [Best Time to Buy and Sell Stock II](https://leetcode.com/explore/interview/card/top-interview-questions-easy/92/array/564/)

The solution was obtained with $O(n)$ complexity in computation, and Space complexity is $O(1)$.

___

```
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        profit = 0
        index = 0
        holding = -1
        while(index < len(prices)-1):
            if((prices[index] < prices[index+1]) & (holding == -1)):
                holding = prices[index]
            elif ((holding != -1) & (prices[index] > prices[index + 1])):
                profit = profit + prices[index] - holding
                holding = -1
            index += 1
        if(holding != -1):
            profit = profit + prices[-1] - holding
        
        return profit
```
___