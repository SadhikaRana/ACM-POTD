# Day 20 - Remove Outermost Parentheses

## Problem
Given a valid parentheses string, remove the outermost parentheses of every primitive substring.

## Approach
- Use a counter (balance) to track open parentheses
- Traverse the string:
  - If '(' → add to result only if balance > 0, then increment balance
  - If ')' → decrement balance first, then add to result only if balance > 0
- This skips outermost parentheses of each primitive

## Complexity
- Time: O(n)
- Space: O(n)

## Code (C++)
```cpp
class Solution {
public:
    string removeOuterParentheses(string s) {
        string result = "";
        int balance = 0;
        
        for (char c : s) {
            if (c == '(') {
                if (balance > 0) result += c;
                balance++;
            } else {
                balance--;
                if (balance > 0) result += c;
            }
        }
        return result;
    }
};
```

## Screenshot
<img width="1919" height="898" alt="image" src="https://github.com/user-attachments/assets/1c1fa6e7-6d0b-4632-b321-fd037d87612b" />

