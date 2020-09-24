# [Fraction to Recurring Decimal](https://leetcode.com/explore/interview/card/top-interview-questions-medium/113/math/821)

Solution from [here.](https://leetcode.com/explore/interview/card/top-interview-questions-medium/113/math/821/discuss/51110/Do-not-use-python-as-cpp-here's-a-short-version-python-code)
___
```python
class Solution:
    def fractionToDecimal(self, numerator, denominator):
        n, remainder = divmod(abs(numerator), abs(denominator))
        sign = '-' if numerator*denominator < 0 else ''
        result = [sign+str(n), '.']
        stack = []
        while remainder not in stack:
            stack.append(remainder)
            n, remainder = divmod(remainder*10, abs(denominator))
            result.append(str(n))

        idx = stack.index(remainder)
        result.insert(idx+2, '(')
        result.append(')')
 
        return ''.join(result).replace('(0)', '').rstrip('.')

```
___