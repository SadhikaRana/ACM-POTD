# Day 17 - Implement Stack using Queues

## Problem
Implement a last-in-first-out (LIFO) stack using only one queue.

## Approach
- Use a single queue to simulate stack behavior
- On push:
  - Insert element into queue
  - Rotate previous elements behind it
- This ensures the newest element always stays at the front
- pop() and top() become O(1)

## Complexity
- Time:
  - push → O(n)
  - pop → O(1)
  - top → O(1)
- Space: O(n)

## Code (C++)

```cpp
class MyStack {
private:
    queue<int> q;
public:
    MyStack() {}
    void push(int x) {
        q.push(x);
        for (int i = 1; i < q.size(); i++) {
            q.push(q.front());
            q.pop();
        }
    }
    int pop() {
        int res = q.front();
        q.pop();
        return res;
    }
    int top() {
        return q.front();
    }
    bool empty() {
        return q.empty();
    }
};
```

## Screenshot
<img width="1915" height="903" alt="image" src="https://github.com/user-attachments/assets/d5250e4a-ed29-48cb-9726-aeaa38989f12" />
