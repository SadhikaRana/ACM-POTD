# Day 7 - Rotate Array

## Problem
Rotate the array to the right by k steps.

## Approach
- Use reverse technique
- Reverse entire array
- Reverse first k elements
- Reverse remaining elements

## Complexity
- Time: O(n)
- Space: O(1)

## Code
```cpp
class Solution {
public:
    void reverse(vector<int>& nums, int start, int end) {
        while(start < end) {
            swap(nums[start], nums[end]);
            start++;
            end--;
        }
    }

    void rotate(vector<int>& nums, int k) {
        int n = nums.size();
        k = k % n;

        reverse(nums, 0, n - 1);
        reverse(nums, 0, k - 1);
        reverse(nums, k, n - 1);
    }
};
```

## Screenshot
<img width="1919" height="899" alt="image" src="https://github.com/user-attachments/assets/be71d73e-e6e8-409f-998b-bda5548a153c" />
