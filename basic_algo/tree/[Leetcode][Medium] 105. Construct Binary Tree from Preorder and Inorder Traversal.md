https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/

#### Algorithm:
Approach 1 (by vmdd): \
Base case: return null if preorder is empty \
Recursive case: Take val = preorder[0] as value at root. Find idx such that inorder[idx] = val. Recursively build left tree using preorder[1, idx+1] and inorder[0, idx]. Simirarily build right tree using the rest of preorder and inorder arrays. \
\
Approach 2: \
Base case: Return null if inorder is empty \
Recursive cases: Take val = preorder[pre_idx] as value at root, where pre_idx starts with 0 and pre_idx += 1 each recursion. Find idx such that inorder[idx] = val. Recursively slice inorder and build left tree using inorder[0 : idx]. Simirarily build right tree using inorder[idx + 1 :]. \
