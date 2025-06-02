# 🧭 Bit Manipulation Algorithm Summary

## 📌 Key Concept

- Bit Manipulation involves using bitwise operations (`&, |, ^, <<, >>`) to solve problems efficiently.
- Often used in problems involving **masks, toggling, counting bits, or optimizing space**.

---

## [Leetcode 136. Single Number](https://leetcode.com/problems/single-number/) [2025-06-02]

```c
int singleNumber(int* nums, int numsSize) {
    int result = 0;
    for (int i = 0; i < numsSize; i++) {
        result ^= nums[i];
    }
    return result;
}
```

- XOR cancels out duplicate numbers, leaving the unique one.

---

## 🔧 When to Use

- Checking parity or bit presence
- Subset generation via bitmasks
- Space-optimized algorithms (e.g., flags, visited sets)

---

## 📈 Time Complexity

- Bitwise operations: **O(1)**
- Overall algorithm: **O(n)** depending on the use case
