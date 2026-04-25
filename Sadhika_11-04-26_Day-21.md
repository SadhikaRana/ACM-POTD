# Day 21 - Make The String Great

## Problem
Given a string of lower and upper case English letters, remove adjacent characters where one is lowercase and the other is the same letter in uppercase.

## Approach
- Use a string as a stack
- Traverse each character:
  - If stack is not empty and the difference between current char and last char is 32 → remove (pop)
  - Else → add (push)
- ASCII difference between lowercase and uppercase of same letter is 32

## Complexity
- Time: O(n)
- Space: O(n)

## Code (C++)
```cpp
class Solution {
public:
    string makeGood(string s) {
        string st;
        
        for (char c : s) {
            if (!st.empty() && abs(st.back() - c) == 32) {
                st.pop_back();
            } else {
                st += c;
            }
        }
        return st;
    }
};
```

## Screenshot
<img width="1918" height="892" alt="image" src="https://github.com/user-attachments/assets/fb1f8844-b2d6-4bd0-a367-1a530838cb9f" />
