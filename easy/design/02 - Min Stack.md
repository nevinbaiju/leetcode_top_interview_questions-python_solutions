# [Min Stack](https://leetcode.com/explore/interview/card/top-interview-questions-easy/98/design/562/)

The two stack approach, all operations happen in constant time. Credits to [this post](https://leetcode.com/explore/interview/card/top-interview-questions-easy/98/design/562/discuss/761397/Python-Solution-Find-min-using-another-Stack)

___
```python
class MinStack:

	def __init__(self):
		"""
		initialize your data structure here.
		"""
		self.stack = []
		self.minVal = float('inf')
		self.minStack = [self.minVal]


	def push(self, x):
		self.stack.append(x)
		if x <= self.minVal:
		    self.minVal = x
		    self.minStack.append(self.minVal)

	def pop(self):
		if self.stack.pop() == self.minVal:
		    self.minStack.pop()
		    self.minVal = self.minStack[-1]


	def top(self):
		return self.stack[-1]

	def getMin(self):
		return self.minVal
```
___