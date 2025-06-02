# 🧭 Queue Algorithm Summary

## 📌 Key Concept

- A **Queue** is a FIFO (First In, First Out) data structure.
- Supports `enqueue`, `dequeue`, and `peek` operations.
- Useful for **BFS traversal**, **task scheduling**, and **sliding window problems**.

---

## [Leetcode 933. Number of Recent Calls](https://leetcode.com/problems/number-of-recent-calls/) [2025-06-02]

```cpp
class RecentCounter {
public:
    queue<int> q;
    RecentCounter() {}

    int ping(int t) {
        q.push(t);
        while (q.front() < t - 3000) q.pop();
        return q.size();
    }
};
```

- Maintains a queue of timestamps within a 3000ms window.

---

## 🔧 When to Use

- Level-order traversal (BFS)
- Rate limiting or fixed-size window tracking
- Real-time event processing

---

## 📈 Time Complexity

- Enqueue/Dequeue: **O(1)**
- BFS traversal: **O(n)**
