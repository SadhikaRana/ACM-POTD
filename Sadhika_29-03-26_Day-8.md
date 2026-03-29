# Day 8 - Reverse Linked List

## Problem
Reverse a singly linked list and return the new head.

## Approach
- Use three pointers: prev, curr, next
- Reverse links one by one
- Move forward until list ends

## Complexity
- Time: O(n)
- Space: O(1)

## Code
```cpp
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        ListNode* prev = nullptr;
        ListNode* curr = head;

        while (curr) {
            ListNode* next = curr->next;
            curr->next = prev;
            prev = curr;
            curr = next;
        }

        return prev;
    }
};
```

## Screenshot
<img width="1919" height="898" alt="image" src="https://github.com/user-attachments/assets/5f3fc1f9-8a54-4254-b3e2-3b36b1a638b1" />
