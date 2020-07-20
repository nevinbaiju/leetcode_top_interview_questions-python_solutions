# [String to Integer (atoi)](https://leetcode.com/explore/interview/card/top-interview-questions-easy/127/strings/884/)

The solution was obtained by first cleaning the string of unwanted characters (blank spaces, remaining characters, ignoring everything else after another character is encountered after seeing the first number.).

The solution runs with a worst case computational complexity of O(n). The memory complexity will also be the same as no new memory, other than to store the result is used.

```python
class Solution:
    def __init__(self):
        self.number_map = {
            "0": 0,
            "1": 1,
            "2": 2,
            "3": 3,
            "4": 4,
            "5": 5,
            "6": 6,
            "7": 7,
            "8": 8,
            "9": 9,
        }
            
    def getNumberStr(self, str: str) -> int:
        number_str = ""
        starting_sign = False
        for char in str:
            if (((char == '+') or (char == '-')) and not (starting_sign)):
                number_str = number_str + char
                starting_sign = True
            elif (char == " ") and not(starting_sign):
                continue
            elif char.isnumeric():
                starting_sign = True
                number_str = number_str + char
            else:
                return number_str
        return number_str
            
    def myAtoi(self, str: str) -> int:
        number_str = self.getNumberStr(str)
        multiplier  = 1
        number = 0
        try:
            for index in range(len(number_str)-1, -1, -1):
                if(number_str[index] == '-'):
                    return number*-1
                elif(number_str[index] == '+'):
                    return number
                number = number + multiplier*self.number_map[number_str[index]]
                multiplier = multiplier * 10
                assert number < 2**31
            return number
        except AssertionError:
            if number_str[0] == '-':
                return -1 * 2**31
            else:
                return 2**31-1
```            