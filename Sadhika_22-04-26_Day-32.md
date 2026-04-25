# Day 32 - Pascal's Triangle

## Problem
Given an integer `numRows`, return the first `numRows` of Pascal’s Triangle.

In Pascal’s Triangle:
- Each number is the sum of the two numbers directly above it
- First and last elements of every row are always 1

## Approach
- Use a **2D vector** to store the triangle
- For each row:
  - Initialize all elements as 1
  - Update middle elements using:
    previous_row[j-1] + previous_row[j]
- Build row by row

## Complexity
- Time: O(n²)
- Space: O(n²)

## Code (C++)
```cpp
class Solution {
public:
    vector<vector<int>> generate(int numRows) {
        vector<vector<int>> result;
        for (int i = 0; i < numRows; i++) {
            vector<int> row(i + 1, 1);
            for (int j = 1; j < i; j++) {
                row[j] = result[i - 1][j - 1] + result[i - 1][j];
            }
            result.push_back(row);
        }
        
        return result;
    }
};
```

## Screenshot
<img width="1919" height="969" alt="image" src="https://github.com/user-attachments/assets/16870047-26bd-4fb7-a27c-87f1959f7c42" />
