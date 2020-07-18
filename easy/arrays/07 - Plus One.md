# [Plus One](https://leetcode.com/explore/interview/card/top-interview-questions-easy/92/array/559/)

The solution was implemented using recursion with a worst case complexity of O(n).
___
```
def plusOne(digits):
    try:
        if (digits[-1] == 9):
            return plusOne(digits[:-1]) + [0]
        elif (digits[-1] < 9):
            digits[-1] += 1
            return digits
    except IndexError:
        return [1]
```
___