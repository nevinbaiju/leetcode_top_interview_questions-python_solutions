# [Best Time to Buy and Sell Stock](https://leetcode.com/explore/interview/card/top-interview-questions-easy/97/dynamic-programming/572/)

The solution is obtained in O(n) computationally and space is constant.
The solution was dervied from [this discussion](https://leetcode.com/explore/interview/card/top-interview-questions-easy/97/dynamic-programming/572/discuss/39038/Kadane's-Algorithm-Since-no-one-has-mentioned-about-this-so-far-:)-(In-case-if-interviewer-twists-the-input)).

```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        maxCur = 0
        maxSoFar = 0
        for i in range(1, len(prices)):
            maxCur += prices[i] - prices[i-1]
            maxCur = max(0, maxCur)
            maxSoFar = max(maxCur, maxSoFar)
        return maxSoFar
```
