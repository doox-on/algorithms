# 🧭 Linked List Algorithm Summary

## 📌 Key Concept

- A **Linked List** is a linear data structure where each element (node) points to the next.
- Common operations include insertion, deletion, reversal, and cycle detection.
- Useful when **dynamic memory allocation** is needed or frequent insertion/deletion is required.

---

## [Leetcode 206. Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/description/) [2025-06-02]

```c
struct ListNode* reverseList(struct ListNode* head) {
    struct ListNode* prev = NULL;
    struct ListNode* curr = head;
    while (curr) {
        struct ListNode* next = curr->next;
        curr->next = prev;
        prev = curr;
        curr = next;
    }
    return prev;
}
```

- Iteratively reverses the pointers in a singly linked list.

---

## 🔧 When to Use

- When frequent insertions/deletions are needed (especially at head/tail).
- When data size is unknown ahead of time.
- For problems involving sequence manipulation without array constraints.

---

## 📈 Time Complexity

- Traversal: **O(n)**
- Insertion/Deletion at head: **O(1)**
- Search: **O(n)** (no random access)
