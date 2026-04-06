# Day 16 - Implement Queue using Stacks

## Problem

Implement a first-in-first-out (FIFO) queue using only two stacks. The queue should support push, pop, peek, and empty operations.

## Approach

* Use two stacks:

  * `incoming` → for push operations
  * `outgoing` → for pop/peek operations
* Push directly into incoming
* For pop/peek:

  * If outgoing is empty → transfer all elements from incoming to outgoing
  * Then operate from outgoing

## Complexity

* Time:

  * Push: O(1)
  * Pop/Peek: Amortized O(1)
* Space: O(n)

## Code

```cpp
class MyQueue {
private:
    stack<int> incoming, outgoing;
public:
    MyQueue() {}
    void push(int x) {
        incoming.push(x);
    }
    int pop() {
        peek();
        int res = outgoing.top();
        outgoing.pop();
        return res;
    }
    int peek() {
        if (outgoing.empty()) {
            while (!incoming.empty()) {
                outgoing.push(incoming.top());
                incoming.pop();
            }
        }
        return outgoing.top();
    }
    bool empty() {
        return incoming.empty() && outgoing.empty();
    }
};
```

## Screenshot

<img width="1917" height="840" alt="image" src="https://github.com/user-attachments/assets/f3fb6ffe-47dd-4f06-8b47-c6fbeec39bc4" />
