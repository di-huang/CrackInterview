https://leetcode.com/problems/binary-tree-inorder-traversal/

**Algorithm:** <br />
Inorder: left -> root -> right <br />
The base case: return [] if root is null; <br />
The recursive cases: return inorder(root.left) + [root.val] + inorder(root.right) where "+" represents list concatenation; <br />

**Time Complexity** <br />
O(n)
