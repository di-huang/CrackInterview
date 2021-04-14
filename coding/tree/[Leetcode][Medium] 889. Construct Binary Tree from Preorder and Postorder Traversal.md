https://leetcode.com/problems/construct-binary-tree-from-preorder-and-postorder-traversal/

#### Algorithm:
We can't create a unique binary tree using preorder and postorder due to the uncertainty of left or right subtree. This one is a bit harder than LC105 and LC106.<br />
```
# An example:
#     3
#  9    20
# 1 2  15 7
# pre: {3} (9 1 2) (20 15 7)
# post: (1 2 9) (15 7 20) {3}
```
According to the above example, 2nd element of pre is the root of left subtree. "{}" denotes root and "()" denotes subtree, and we can recursively build binary trees based on them. Refer to the above example for index calculation when slicing preorder and postorder.