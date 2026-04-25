# Day 22 - Flood Fill

## Problem
Given an m x n grid representing an image, perform a flood fill starting from a given pixel. Replace all connected pixels (4-directionally) having the same initial color with a new color.

## Approach
- Use DFS (Depth First Search)
- Start from the given pixel (sr, sc)
- Store the original color
- Traverse in 4 directions (up, down, left, right):
  - If the pixel has the same original color → change it
  - Continue DFS recursively
- Avoid revisiting pixels
- Edge case: If original color == new color → return immediately

## Complexity
- Time: O(m × n)
- Space: O(m × n) (recursion stack in worst case)

## Code (C++)
```cpp
class Solution {
public:
    void dfs(vector<vector<int>>& image, int r, int c, int color, int original) {
        int m = image.size(), n = image[0].size();
        
        if (r < 0 || c < 0 || r >= m || c >= n || image[r][c] != original)
            return;
        
        image[r][c] = color;
        
        dfs(image, r+1, c, color, original);
        dfs(image, r-1, c, color, original);
        dfs(image, r, c+1, color, original);
        dfs(image, r, c-1, color, original);
    }
    
    vector<vector<int>> floodFill(vector<vector<int>>& image, int sr, int sc, int color) {
        int original = image[sr][sc];
        if (original == color) return image;
        
        dfs(image, sr, sc, color, original);
        return image;
    }
};
```

## Screenshot
<img width="1919" height="944" alt="image" src="https://github.com/user-attachments/assets/13b9719d-8290-42d7-893b-c8b8abfd05b8" />
