# Day 4 - Missing Number

## Problem
Find the missing number in an array containing numbers from 0 to n.

## Approach
- Use sum formula: n(n+1)/2
- Subtract actual array sum from expected sum
- Result is the missing number

## Complexity
- Time: O(n)
- Space: O(1)

## Code
```cpp
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n = nums.size();
        int expected = n * (n + 1) / 2;
        int actual = 0;
        for (int x : nums) {
            actual += x;
        }
        return expected - actual;
    }
};
```
## Screenshot
<img width="1920" height="955" alt="Screenshot (1188)" src="https://github.com/user-attachments/assets/a9938e3d-8579-4076-a918-ab7fe88db56c" />


