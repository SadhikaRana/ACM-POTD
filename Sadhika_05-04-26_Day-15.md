# Day 15 - Valid Parentheses

## Problem

Given a string containing just '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

## Approach

* Use a stack to track opening brackets
* Push opening brackets onto stack
* For closing brackets:

  * Check if stack is empty → invalid
  * Pop top and check if it matches
* At the end, stack should be empty

## Complexity

* Time: O(n)
* Space: O(n)

## Code

```cpp 
class Solution {
public:
    bool isValid(string s) {
        stack<char> st;
        for (char c : s) {
            if (c == '(' || c == '{' || c == '[') {
                st.push(c);
            } else {
                if (st.empty()) return false;
                char top = st.top();
                st.pop();
                if ((c == ')' && top != '(') ||
                    (c == '}' && top != '{') ||
                    (c == ']' && top != '[')) {
                    return false;
                }
            }
        }
        return st.empty();
    }
};
```

## Screenshot

<img width="1907" height="835" alt="image" src="https://github.com/user-attachments/assets/09b0d67a-4dea-4eee-8433-08e9145f89a6" />

