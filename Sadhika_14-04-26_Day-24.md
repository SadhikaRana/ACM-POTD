# Day 24 - Find Center of Star Graph

## Problem
Given an undirected star graph, find the center node.  
A star graph has one center node connected to all other nodes.

## Approach
- In a star graph, the center appears in every edge
- Compare first two edges:
  - The common node between them is the center
- Check:
  - If edges[0][0] matches any node in edges[1] → it's the center
  - Else → edges[0][1] is the center

## Complexity
- Time: O(1)
- Space: O(1)

## Code (C++)
```cpp
class Solution {
public:
    int findCenter(vector<vector<int>>& edges) {
        if (edges[0][0] == edges[1][0] || edges[0][0] == edges[1][1])
            return edges[0][0];
        return edges[0][1];
    }
};
```

## Screenshot
<img width="1919" height="958" alt="image" src="https://github.com/user-attachments/assets/19e8bdfc-ef48-4507-a340-8b595582dacb" />
