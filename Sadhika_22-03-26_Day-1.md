# Day 1 - Remove Duplicates from Sorted Array

## Problem
Given a sorted array, remove duplicates in-place such that each element appears only once.

## Approach
Used two-pointer technique:
- One pointer tracks unique elements
- Other pointer scans array
- When new element found - place it in correct position

## Complexity
- Time: O(n)
- Space: O(1)


## Code
```cpp
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        if(nums.size() == 0)
            return 0;
        int i = 0;
        for(int j = 1; j < nums.size(); j++) {
            if(nums[j] != nums[i]) {
                i++;
                nums[i] = nums[j];
            }
        }
        return i + 1;
    }
};
```

### 3. Upload Screenshot

<img width="1920" height="968" alt="Screenshot (1160)" src="https://github.com/user-attachments/assets/a66cadbc-556f-42d5-a707-44c037ab8acd" />

