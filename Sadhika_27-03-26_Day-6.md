# Day 6 - Check If N and Its Double Exist

## Problem
Check if there exist two indices i and j such that arr[i] = 2 * arr[j].

## Approach
- Use unordered set
- For each element:
  - Check if double exists
  - If element is even, check if half exists
- If found → return true

## Complexity
- Time: O(n)
- Space: O(n)

## Code
```cpp
class Solution {
public:
    bool checkIfExist(vector<int>& arr) {
        unordered_set<int> st;

        for (int num : arr) {
            if (st.count(2 * num) || (num % 2 == 0 && st.count(num / 2))) {
                return true;
            }
            st.insert(num);
        }

        return false;
    }
};
```

## Screenshot
<img width="1910" height="903" alt="image" src="https://github.com/user-attachments/assets/a61a5790-06d6-420f-b491-32a7a01c3c02" />
