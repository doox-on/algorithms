# 🧭 Stack Algorithm Summary

## 📌 Key Concept

- A **Stack** is a LIFO (Last In, First Out) data structure.
- Supports `push`, `pop`, and `peek` operations.
- Commonly used for **backtracking**, **expression evaluation**, and **function call management**.

---

## [Leetcode 20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/description/) [2025-06-02]

```cpp
bool isValid(string s) {
    stack<char> st;
    for (char c : s) {
        if (c == '(' || c == '[' || c == '{') st.push(c);
        else {
            if (st.empty()) return false;
            char top = st.top(); st.pop();
            if ((c == ')' && top != '(') ||
                (c == ']' && top != '[') ||
                (c == '}' && top != '{')) return false;
        }
    }
    return st.empty();
}
```

- Uses a stack to track open brackets and validate matching closing brackets.

---

## 🔧 When to Use

- Parsing nested structures
- Undo functionality
- Backtracking and recursion emulation

---

## 📈 Time Complexity

- Push/Pop/Peek: **O(1)**
- Overall: **O(n)** for most traversal problems
