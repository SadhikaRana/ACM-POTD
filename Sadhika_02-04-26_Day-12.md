# Day 12 - Remove Duplicates from Sorted List

## Problem

Given the head of a sorted linked list, delete all duplicates such that each element appears only once.

## Approach

* Traverse the linked list using a pointer
* Compare current node with next node
* If values are same → skip the next node
* Else → move forward
* Continue until end of list

## Complexity

* Time: O(n)
* Space: O(1)

## Code

```cpp
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        if (!head) return nullptr;
        ListNode* current = head;
        while (current && current->next) {
            if (current->val == current->next->val) {
                current->next = current->next->next;
            } else {
                current = current->next;
            }
        }
        return head;
    }
};
```

## Screenshot
<img width="1914" height="899" alt="image" src="https://github.com/user-attachments/assets/5b2ed71a-d0b7-4e27-be44-a8a391598304" />

