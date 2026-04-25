# Day 19 - Backspace String Compare

## Problem
Given two strings, determine if they are equal after applying backspace operations (`#`).

## Approach
- Traverse both strings from the end
- Skip characters affected by backspaces
- Compare valid characters one by one
- If mismatch → return false, else continue

## Complexity
- Time: O(n + m)
- Space: O(1)

## Code (C++)
```cpp
class Solution {
private:
    int getNextValidChar(string& s, int index) {
        int backspace = 0;
        while (index >= 0) {
            if (s[index] == '#') {
                backspace++;
            } else if (backspace > 0) {
                backspace--;
            } else {
                break;
            }
            index--;
        }
        return index;
    }
    
public:
    bool backspaceCompare(string s, string t) {
        int i = s.length() - 1, j = t.length() - 1;
        
        while (i >= 0 || j >= 0) {
            i = getNextValidChar(s, i);
            j = getNextValidChar(t, j);
            
            if (i >= 0 && j >= 0 && s[i] != t[j]) {
                return false;
            }
            if ((i >= 0) != (j >= 0)) {
                return false;
            }
            i--;
            j--;
        }
        return true;
    }
};
```

## Screenshot
<img width="1911" height="911" alt="image" src="https://github.com/user-attachments/assets/f79a508a-350b-4653-ae05-2ca766efbbff" />

