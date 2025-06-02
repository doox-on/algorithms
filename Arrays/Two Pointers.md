# 🧭 Two Pointer Algorithm Summary

## 📌 Key Concept

- **Two Pointer** is a technique where you use two indices (or pointers) to traverse a data structure, usually a **sorted array** or **string**, to solve problems efficiently in **O(n)** time.
- One pointer starts at the **beginning**, the other at the **end**, and both move toward each other based on some condition.

---
## [Leetcode 28. Find the Index of the First Occurrence in a String](https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/description/?envType=problem-list-v2&envId=two-pointers) [2025-06-02]

```c
#include <string.h>

int strStr(char* haystack, char* needle) {
    char* p = strstr(haystack, needle);

    if ( p != NULL) {
        return p - haystack;
    } 
    
    return -1;

}
```
- I could solve it with two pointer method using index i and j, but it's brute force.
- **KMP** can be a good option, but used strstr.
- The point is, memory address difference btw p and haystack is the index difference. 

---



## 🔧 When to Use

- The input is **sorted** (array or string)
- You're finding **pairs**, **subarrays**, or **ranges** that meet certain conditions
- You're working with **palindromes**, **duplicates**, **window sums**, etc.

---

## 📈 Time Complexity

- Typically **O(n)** for linear scan
- Often more efficient than brute force (**O(n²)**)

---

## 🧪 Common Variants

| Variant | Use Case |
|--------|----------|
| Start-End | `left = 0, right = n - 1` → for sum-based problems |
| Forward-Forward | `i = 0, j = 0` → for sliding window problems |
| Bidirectional | Matching from both ends (e.g., palindrome checks) |

---

