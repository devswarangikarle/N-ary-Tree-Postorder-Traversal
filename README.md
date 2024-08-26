# N-ary-Tree-Postorder-Traversal

Given the root of an n-ary tree, return the postorder traversal of its nodes' values.
N-aryTree input serialization is represented in their level order traversal. Each group of children is separated by the null value
Constraints:
The number of nodes in the tree is in the range [0, 104].
0 <= Node.val <= 104
The height of the n-ary tree is less than or equal to 1000.

class Solution(object):
    def postorder(self, root):
        # If the root is None, return an empty list
        if not root:
            return []

        res = []

        def dfs(root):
            for x in root.children:
                dfs(x)
            res.append(root.val)

        dfs(root)

        return res
