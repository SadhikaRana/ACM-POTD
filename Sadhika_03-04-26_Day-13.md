# Day 13 - Intersection of Two Linked Lists

## Problem

Given the heads of two singly linked lists, return the node at which the two lists intersect. If they do not intersect, return null.

## Approach

* Use two pointers (pA and pB)
* Traverse both lists
* When a pointer reaches end, redirect it to the head of the other list
* This equalizes path length
* If intersection exists → pointers meet
* Else → both reach null

## Complexity

* Time: O(n + m)
* Space: O(1)

## Code

```cpp
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        if (!headA || !headB) return nullptr;
        ListNode *pA = headA, *pB = headB;
        while (pA != pB) {
            pA = pA ? pA->next : headB;
            pB = pB ? pB->next : headA;
        }
        return pA;
    }
};
```

## Screenshot

<img width="1917" height="836" alt="image" src="https://github.com/user-attachments/assets/81dd232c-c4cd-49e6-a0f8-c66003e4d349" />

