# Day 34 - House Robber

## Problem
You are a robber planning to rob houses along a street.

Each house has some money, but **adjacent houses cannot be robbed together**.

Given an array `nums`, return the **maximum amount of money** you can rob without alerting the police.

## Approach
- Classic **Dynamic Programming** problem
- At each house, you have two choices:
  - Rob it → add current value + value from i-2
  - Skip it → take value from i-1
- Transition:
  max(i) = max(nums[i] + max(i-2), max(i-1))
- Use **space optimization** with two variables

## Complexity
- Time: O(n)
- Space: O(1)

## Code (C++)
```cpp
class Solution {
public:
    int rob(vector<int>& nums) {
        if (nums.empty()) return 0;
        if (nums.size() == 1) return nums[0];
        int prev1 = nums[0], prev2 = 0;
        for (int i = 1; i < nums.size(); i++) {
            int current = max(nums[i] + prev2, prev1);
            prev2 = prev1;
            prev1 = current;
        }
        return prev1;
    }
};
```

## Screenshot
<img width="1910" height="948" alt="image" src="https://github.com/user-attachments/assets/86a0a81f-5460-42b1-a9e4-9ec9785f7b5d" />
