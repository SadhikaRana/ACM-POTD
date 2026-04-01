# Day 11 - Merge Two Sorted Lists

## Problem
Merge two sorted linked lists into one sorted list.

## Approach
- Use a dummy node to simplify handling
- Compare nodes from both lists
- Attach smaller node to result
- Continue until one list ends
- Attach remaining nodes

## Complexity
- Time: O(n + m)
- Space: O(1)

## Code
```cpp
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) {
        ListNode* dummy = new ListNode(0);
        ListNode* current = dummy;

        while (list1 && list2) {
            if (list1->val <= list2->val) {
                current->next = list1;
                list1 = list1->next;
            } else {
                current->next = list2;
                list2 = list2->next;
            }
            current = current->next;
        }

        current->next = list1 ? list1 : list2;

        return dummy->next;
    }
};
```
## Screenshot
<img width="1919" height="891" alt="image" src="https://github.com/user-attachments/assets/b90f1a8a-fd65-4231-96e1-6c0602b21545" />
