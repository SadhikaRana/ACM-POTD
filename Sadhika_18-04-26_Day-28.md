# Day 28 - Subtree of Another Tree

## Problem
Given the roots of two binary trees `root` and `subRoot`, return true if there is a subtree of `root` with the same structure and node values as `subRoot`.

## Approach
- Traverse the main tree
- At each node:
  - Check if the subtree rooted at that node is identical to `subRoot`
- Use a helper function `isSame()`:
  - If both nodes are NULL → true
  - If one is NULL → false
  - Compare values and recursively check left & right
- If match found anywhere → return true

## Complexity
- Time: O(n * m)
- Space: O(h)

## Code (C++)
```cpp
class Solution {
public:
    bool isSame(TreeNode* s, TreeNode* t) {
        if (!s && !t) return true;
        if (!s || !t) return false;
        return s->val == t->val &&
               isSame(s->left, t->left) &&
               isSame(s->right, t->right);
    }
    bool isSubtree(TreeNode* root, TreeNode* subRoot) {
        if (!root) return false;
        if (isSame(root, subRoot)) return true;
        return isSubtree(root->left, subRoot) ||
               isSubtree(root->right, subRoot);
    }
};
```

## Screenshot
<img width="1919" height="901" alt="image" src="https://github.com/user-attachments/assets/08437e66-a5c1-461f-81b9-7ed738025d1c" />
