# Day 18 - Remove All Adjacent Duplicates in String

## Problem
Given a string, repeatedly remove adjacent duplicate characters until no duplicates remain.

## Approach
- Use a string as a stack
- Traverse each character:
  - If it matches the last character → remove (pop)
  - Else → add (push)
- This ensures adjacent duplicates are removed dynamically

## Complexity
- Time: O(n)
- Space: O(n)

## Code (C++)

```cpp
class Solution {
public:
    string removeDuplicates(string s) {
        string st = "";
        for (char c : s) {
            if (!st.empty() && st.back() == c) {
                st.pop_back();
            } else {
                st.push_back(c);
            }
        }
        return st;
    }
};
```

## Screenshot
<img width="1918" height="900" alt="image" src="https://github.com/user-attachments/assets/918cc643-e1cf-450a-9b9b-c8c6c6220585" />

