# Day 29 - Fibonacci Number

## Problem
The Fibonacci sequence is defined as:
- F(0) = 0  
- F(1) = 1  
- F(n) = F(n-1) + F(n-2), for n > 1  

Given `n`, return F(n).

## Approach
- Use an **iterative approach** instead of recursion (to avoid exponential time)
- Maintain two variables:
  - `a` → F(n-2)
  - `b` → F(n-1)
- Loop from 2 to n:
  - Compute next value
  - Shift variables forward
- Return the final value

## Complexity
- Time: O(n)
- Space: O(1)

## Code (C++)
```cpp
class Solution {
public:
    int fib(int n) {
        if (n <= 1) return n;
        int a = 0, b = 1;
        for (int i = 2; i <= n; i++) {
            int c = a + b;
            a = b;
            b = c;
        }
        return b;
    }
};
```

## Screenshot
<img width="1900" height="939" alt="image" src="https://github.com/user-attachments/assets/7a0218fd-ceb4-4d66-8dce-0145b74c9979" />
