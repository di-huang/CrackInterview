#### Algorithm
Base case: return null if preorder is empty \
Recursive case: Take val = preorder[0] as value at root. Find idx such that inorder[idx] = val. Recursively build left tree using preorder[1, idx+1] and inorder[0, idx]. Simirarily build right tree using the rest of preorder and inorder arrays.
