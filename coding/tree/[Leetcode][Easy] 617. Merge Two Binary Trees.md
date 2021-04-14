https://leetcode.com/problems/merge-two-binary-trees/

**Algorithm:** <br />
```python
def mergeTrees(root1, root2):
    if root1 is None:
        return root2
    if root2 is None:
        return root1

    root1.val += root2.val
    root1.left = mergeTrees(root1.left, root2.left)
    root1.right = mergeTrees(root1.right, root2.right)
    return root1
```

**Time Complexity** <br />
O(n)
