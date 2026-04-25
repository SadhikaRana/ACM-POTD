# Day 30 - Power of Two

## Problem
Given an integer `n`, return true if it is a power of two. Otherwise, return false.

An integer `n` is a power of two if there exists an integer `x` such that:
n = 2^x

## Approach
- A power of two has exactly **one set bit** in binary
- Example:
  - 1  → 0001
  - 2  → 0010
  - 4  → 0100
  - 8  → 1000
- Trick:
  - `n & (n - 1)` removes the lowest set bit
  - For powers of two → result becomes 0
- Also ensure `n > 0`

## Complexity
- Time: O(1)
- Space: O(1)

## Code (C++)
```cpp
class Solution {
public:
    bool isPowerOfTwo(int n) {
        return n > 0 && (n & (n - 1)) == 0;
    }
};
```

## Screenshot
<img width="1910" height="957" alt="image" src="https://github.com/user-attachments/assets/b0b74579-dfb6-42b7-91b9-0901afcf251d" />
