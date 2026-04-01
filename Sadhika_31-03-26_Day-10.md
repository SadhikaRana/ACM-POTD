# Day 10 - Middle of the Linked List

## Problem
Find the middle node of a linked list. If there are two middle nodes, return the second one.

## Approach
- Use two pointers (slow and fast)
- Slow moves 1 step, fast moves 2 steps
- When fast reaches end, slow is at middle

## Complexity
- Time: O(n)
- Space: O(1)

## Code
```cpp
class Solution {
public:
    ListNode* middleNode(ListNode* head) {
        ListNode* slow = head;
        ListNode* fast = head;

        while (fast && fast->next) {
            slow = slow->next;
            fast = fast->next->next;
        }

        return slow;
    }
};
```

## Screenshot
<img width="1910" height="904" alt="image" src="https://github.com/user-attachments/assets/5715ae00-483d-454e-b126-e65a77e7b405" />
