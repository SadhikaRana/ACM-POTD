# Day 31 - Climbing Stairs

## Problem
You are climbing a staircase. It takes `n` steps to reach the top.

Each time you can either climb **1 step or 2 steps**.  
Return the number of distinct ways to reach the top.

## Approach
- This is a classic **Fibonacci pattern**
- To reach step `n`, you can come from:
  - step `n-1` (1 step jump)
  - step `n-2` (2 step jump)
- So:
  ways(n) = ways(n-1) + ways(n-2)
- Use **iterative DP (space optimized)** instead of recursion

## Complexity
- Time: O(n)
- Space: O(1)

## Code (C++)
```cpp
class Solution {
public:
    int climbStairs(int n) {
        if (n <= 2) return n;
        int prev = 1, curr = 2;
        for (int i = 3; i <= n; i++) {
            int temp = prev + curr;
            prev = curr;
            curr = temp;
        }
        return curr;
    }
};
```

## Screenshot
<img width="1919" height="963" alt="image" src="https://github.com/user-attachments/assets/3819dbe1-f752-4275-9354-9942ed649856" />
