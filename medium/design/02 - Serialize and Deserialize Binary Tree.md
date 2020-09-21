# [Serialize and Deserialize Binary Tree](https://leetcode.com/explore/interview/card/top-interview-questions-medium/112/design/812)
___
```python
class Codec:
    def trim_ends(self, result):
        for i, val in enumerate(result):
            if val:
                last_index = i
                
        return result[:last_index+1]
    def serialize(self, root):
        """Encodes a tree to a single string.
        
        :type root: TreeNode
        :rtype: str
        """
        
        if not root:
            return []
        stack = [root]
        result = []
        while stack:
            # self.print_stack(stack)
            current = stack.pop(0)
            if not current:
                result.append(None)
                continue
            result.append(current.val)
            stack.append(current.left)
            stack.append(current.right)
        
        return self.trim_ends(result)

    def deserialize(self, data):
        """Decodes your encoded data to tree.
        
        :type data: str
        :rtype: TreeNode
        """
        if not data:
            return []
        print(data)
        node_list = []
        for val in data:
            node_list.append(TreeNode(val))
        for i, node in enumerate(node_list):
            if node:
                try:
                    node.left = node_list[(i*2)+1]
                    node.right = node_list[(i*2)+2]
                except IndexError:
                    pass
                
        return node_list[0]
```
>Accepted solution from the community.

```python
class Codec:
    def serialize(self, root):    
        if not root: return ""
        q = collections.deque([root])
        res = []
        while q:
            node = q.popleft()
            if node:
                q.append(node.left)
                q.append(node.right)
            res.append(str(node.val) if node else '#')
        return ','.join(res)
                
    
    def deserialize (self, data):
        if not data: return None
        nodes = data.split(',')
        root = TreeNode(int(nodes[0]))
        q = collections.deque([root])
        index = 1
        while q:
            node = q.popleft()
            if nodes[index] is not '#':
                node.left = TreeNode(int(nodes[index]))
                q.append(node.left)
            index += 1
        
            if nodes[index] is not '#':
                node.right = TreeNode(int(nodes[index]))
                q.append(node.right)
            index += 1
        return root
```
___