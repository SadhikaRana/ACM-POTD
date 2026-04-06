# Day 14 - Palindrome Linked List

## Problem

Given the head of a singly linked list, return true if it is a palindrome, otherwise false.

## Approach

* Use slow and fast pointers to find the middle of the list
* Reverse the second half of the list
* Compare first half and reversed second half
* If all values match → palindrome

## Complexity

* Time: O(n)
* Space: O(1)

## Code

```cpp
class Solution {
public:
    bool isPalindrome(ListNode* head) {
        if (!head || !head->next) return true;
        ListNode* slow = head, *fast = head;
        while (fast && fast->next) {
            slow = slow->next;
            fast = fast->next->next;
        }
        ListNode* prev = nullptr;
        while (slow) {
            ListNode* next = slow->next;
            slow->next = prev;
            prev = slow;
            slow = next;
        }
        ListNode* left = head, *right = prev;
        while (right) {
            if (left->val != right->val) return false;
            left = left->next;
            right = right->next;
        }
        return true;
    }
};
```

## Screenshot
<img width="1884" height="793" alt="image" src="https://github.com/user-attachments/assets/ac87bc78-6cce-40fb-990c-18afc3baad66" />
