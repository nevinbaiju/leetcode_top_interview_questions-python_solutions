# [Evaluate Reverse Polish Notation](https://leetcode.com/explore/interview/card/top-interview-questions-medium/114/others/823/)

The extra divide function is because their trunc function was working in a very weird manner from my python.
___
```python
class Solution(object):
    def divide_round(self, operands):
        operand_1, operand_2 = operands
        result = math.trunc(abs(operand_1) / abs(operand_2))
        if operand_1 < 0:
            result *= -1
        if operand_2 < 0:
            result *= -1
            
        return result
    
    def evalRPN(self, tokens):
        """
        :type tokens: List[str]
        :rtype: int
        """
        op_dict = {
            '+': lambda operands: operands[0] + operands[1],
            '-': lambda operands: operands[0] - operands[1],
            '*': lambda operands: operands[0] * operands[1],
            '/': self.divide_round,
        }
        stack = []
        while(tokens):
            current_token = tokens.pop(0)
            if op_dict.get(current_token, False):
                operand_2 = stack.pop()
                operand_1 = stack.pop()
                result = op_dict[current_token]((operand_1, operand_2))
                stack.append(result)
            else:
                stack.append(int(current_token))
        result = math.trunc(stack.pop())
        
        return result
```
___