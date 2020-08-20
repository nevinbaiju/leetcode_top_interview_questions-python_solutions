# [Add Two Numbers](https://leetcode.com/explore/interview/card/top-interview-questions-medium/107/linked-list/783/)

This result is bad, eventhough it runs at O(n) there are a lot of redundant lines of code which should be optimized.

```python
class Solution:
    def length(self, l1: ListNode):
        length = 0
        while(l1):
            length += 1
            l1 = l1.next
        return length
    def insert_at_end(self, l1: ListNode, val):
        while(l1.next):
            l1 = l1.next
        l1.next = ListNode(val)
    def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
        if self.length(l1) <= self.length(l2):
            result_head = l2
        else:
            result_head = l1
        remainder = 0
        result = result_head
        while(l1 and l2):
            sum_val = l1.val + l2.val + remainder
            remainder = sum_val // 10
            sum_val %= 10
            result.val = sum_val
            
            l1 = l1.next
            l2 = l2.next
            result = result.next
        
        while remainder:
            if result:
                sum_val = result.val + remainder
                remainder = sum_val // 10
                sum_val %= 10

                result.val = sum_val
                result = result.next
            else:
                self.insert_at_end(result_head, 1)
                break
            
        return result_head
```

However, [this solution](https://leetcode.com/explore/interview/card/top-interview-questions-medium/107/linked-list/783/discuss/1016/Clear-python-code-straight-forward) is very clean.
