# Day 33 - Min Cost Climbing Stairs

## Problem
You are given an integer array `cost` where `cost[i]` is the cost of the i-th step.

Once you pay the cost, you can climb either **1 step or 2 steps**.

You can start from index `0` or `1`.

Return the **minimum cost** to reach the top of the floor.

## Approach
- This is a **Dynamic Programming (Fibonacci-like)** problem
- At each step, you can come from:
  - previous step (i-1)
  - or two steps before (i-2)
- So:
  cost[i] = cost[i] + min(cost[i-1], cost[i-2])
- Use **space optimization** by keeping only two variables

## Complexity
- Time: O(n)
- Space: O(1)

## Code (C++)
```cpp
class Solution {
public:
    int minCostClimbingStairs(vector<int>& cost) {
        int n = cost.size();
        int prev1 = cost[0], prev2 = cost[1];
        for (int i = 2; i < n; i++) {
            int current = cost[i] + min(prev1, prev2);
            prev1 = prev2;
            prev2 = current;
        }
        return min(prev1, prev2);
    }
};
```

## Screenshot
<img width="1913" height="943" alt="image" src="https://github.com/user-attachments/assets/1728ecc7-f0a0-44f9-a553-81d7a01e923c" />
