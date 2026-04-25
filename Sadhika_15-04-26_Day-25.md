# Day 25 - Maximum Depth of Binary Tree

## Problem
Given the root of a binary tree, return its maximum depth.  
The maximum depth is the number of nodes along the longest path from the root down to the farthest leaf node.

## Approach
- Use recursion (DFS)
- Base case:
  - If node is NULL → return 0
- For each node:
  - Compute depth of left subtree
  - Compute depth of right subtree
  - Return 1 + max(left, right)

## Complexity
- Time: O(n)
- Space: O(h) (recursion stack, h = height of tree)

## Code (C++)
```cpp
class Solution {
public:
    int maxDepth(TreeNode* root) {
        if (!root) return 0;
        return 1 + max(maxDepth(root->left), maxDepth(root->right));
    }
};
```

## Screenshot
<img width="1919" height="951" alt="image" src="https://github.com/user-attachments/assets/1da1f486-f6e9-4937-ae43-dea12269c3d9" />
