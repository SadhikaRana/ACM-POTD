# Day 2 - Two Sum

## Problem
Find two indices such that their values add up to target.

## Approach
Used Hash Map:
- Store value and index
- Check if (target - current) exists
- If yes → return indices

## Complexity
- Time: O(n)
- Space: O(n)

## Code
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> mp;

        for (int i = 0; i < nums.size(); i++) {
            int complement = target - nums[i];

            if (mp.find(complement) != mp.end()) {
                return {mp[complement], i};
            }

            mp[nums[i]] = i;
        }

        return {};
    }
};
```
## Screenshot 
<img width="1920" height="965" alt="Screenshot (1180)" src="https://github.com/user-attachments/assets/c3f4fba0-10c5-4480-b248-17162c5ed59b" />













