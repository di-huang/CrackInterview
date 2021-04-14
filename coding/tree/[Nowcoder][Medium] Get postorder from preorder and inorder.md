https://www.nowcoder.com/questionTerminal/5ae5174f17674e458028ce12bc8bfe0b

**Algorithm:** <br />
This question is similar to LC 105. We don't have to construct tree for this one. <br />
Base case: Return null if inorder is empty
Recursive cases: Take val = preorder[pre_idx] as value at root, where pre_idx starts with 0 and pre_idx += 1 each recursion. Find idx such that inorder[idx] = val. Recursively slice inorder for left tree -> inorder[0 : idx]. Similarly for right tree -> inorder[idx + 1 :]. Append node.val to postorder sequence in each recursion.
