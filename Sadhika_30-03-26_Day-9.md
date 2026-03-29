# Day 9 - Linked List Cycle

## Problem
Determine if a linked list has a cycle.

## Approach
- Use two pointers (slow and fast)
- Slow moves 1 step, fast moves 2 steps
- If they meet → cycle exists

## Complexity
- Time: O(n)
- Space: O(1)

## Code
```cpp
class Solution {
public:
    bool hasCycle(ListNode *head) {
        if (!head) return false;

        ListNode *slow = head;
        ListNode *fast = head;

        while (fast && fast->next) {
            slow = slow->next;
            fast = fast->next->next;

            if (slow == fast) {
                return true;
            }
        }

        return false;
    }
};
```

## Screenshot
<img width="1919" height="901" alt="image" src="https://github.com/user-attachments/assets/23aea6ea-e040-44ed-bbf2-fbb8be1910e1" />
