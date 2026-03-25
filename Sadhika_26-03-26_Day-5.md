# Day 5 - Move Zeroes

## Problem
Move all zeroes to the end while maintaining the order of non-zero elements.

## Approach
- Use two pointers
- One pointer tracks position for non-zero elements
- Swap non-zero elements to front

## Complexity
- Time: O(n)
- Space: O(1)

## Code
```cpp
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int i = 0;

        for(int j = 0; j < nums.size(); j++) {
            if(nums[j] != 0) {
                swap(nums[i], nums[j]);
                i++;
            }
        }
    }
};
```
## Screenshot
<img width="1912" height="887" alt="image" src="https://github.com/user-attachments/assets/da6ba9a1-9b6f-4b7a-a75c-5e7574170750" />
