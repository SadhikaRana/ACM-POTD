# Day 26 - Invert Binary Tree

## Problem
Given the root of a binary tree, invert the tree and return its root.

## Approach
- Use recursion (DFS)
- Base case:
  - If node is NULL → return NULL
- Swap left and right child of current node
- Recursively invert left and right subtrees

## Complexity
- Time: O(n)
- Space: O(h) (recursion stack, h = height of tree)

## Code (C++)
```cpp
class Solution {
public:
    TreeNode* invertTree(TreeNode* root) {
        if (!root) return nullptr;
        swap(root->left, root->right);
        invertTree(root->left);
        invertTree(root->right);
        return root;
    }
};
```

## Screenshot
<img width="1910" height="958" alt="image" src="https://github.com/user-attachments/assets/dcffbe48-dc46-4811-81eb-8c0f32b47f7b" />
