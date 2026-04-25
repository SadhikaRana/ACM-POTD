# Day 23 - Find the Town Judge

## Problem
In a town of n people labeled from 1 to n, find the town judge.  
The judge trusts nobody, and everybody else trusts the judge.

## Approach
- Use two arrays:
  - `in[i]` → number of people who trust person i
  - `out[i]` → number of people person i trusts
- Traverse trust list:
  - Increase out[a]
  - Increase in[b]
- Judge condition:
  - in[i] == n - 1
  - out[i] == 0
- Return the person satisfying both, else return -1

## Complexity
- Time: O(n + m)
- Space: O(n)

## Code (C++)
```cpp
class Solution {
public:
    int findJudge(int n, vector<vector<int>>& trust) {
        vector<int> in(n+1, 0), out(n+1, 0);
        for (auto &t : trust) {
            out[t[0]]++;
            in[t[1]]++;
        }
        for (int i = 1; i <= n; i++) {
            if (in[i] == n - 1 && out[i] == 0)
                return i;
        }
        return -1;
    }
};
```

## Screenshot
<img width="1916" height="953" alt="image" src="https://github.com/user-attachments/assets/1417ea35-90c3-47eb-a7ba-2fc930fb351f" />
