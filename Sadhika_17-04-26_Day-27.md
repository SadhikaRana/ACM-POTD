# Day 27 - Diameter of Binary Tree

## Problem
Given the root of a binary tree, return the length of the diameter of the tree.  
The diameter is the length of the longest path between any two nodes in the tree.

## Approach
- Use DFS to compute height of each subtree
- For every node:
  - Calculate left height (l)
  - Calculate right height (r)
  - Update diameter = max(diameter, l + r)
- Return height = 1 + max(l, r)
- Final answer is the maximum diameter found

## Complexity
- Time: O(n)
- Space: O(h) (recursion stack)

## Code (C++)
```cpp
class Solution {
public:
    int diameterOfBinaryTree(TreeNode* root) {
        int ans = 0;
        function<int(TreeNode*)> height = [&](TreeNode* node) {
            if (!node) return 0;
            int l = height(node->left);
            int r = height(node->right);
            ans = max(ans, l + r);
            return 1 + max(l, r);
        };
        height(root);
        return ans;
    }
};
```

## Screenshot
<img width="1912" height="956" alt="image" src="https://github.com/user-attachments/assets/6fc6c30d-e011-4d02-8297-d698b1d0ffc5" />
