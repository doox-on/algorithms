# 🧭 Sliding Window Algorithm Summary

## 📌 Key Concept

- **Sliding Window** is a technique for problems involving **contiguous subarrays or substrings** in arrays/strings.
- It uses a **window of variable or fixed size** that slides across the input, avoiding redundant computation.
- Ideal for **sum, average, max/min, or frequency count** problems.

---

## [Leetcode 3. Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/description/) [2025-06-02]

```c
int lengthOfLongestSubstring(char* s) {
    int map[128] = {0};
    int left = 0, right = 0;
    int maxLen = 0;

    while (s[right]) {
        map[(int)s[right]]++;

        while (map[(int)s[right]] > 1) {
            map[(int)s[left]]--;
            left++;
        }

        int windowLen = right - left + 1;
        if (windowLen > maxLen) {
            maxLen = windowLen;
        }

        right++;
    }

    return maxLen;
}
```

- Two pointers (`left`, `right`) define the **sliding window**.
- Expand `right`, and **shrink `left` only when condition breaks** (duplicate found).
- Efficiently keeps track of the window state using a hash map.

---

## 🔧 When to Use

- You need to find **subarrays or substrings** that satisfy certain conditions.
- The input is **sequential** and conditions involve **length, sum, frequency**, etc.
- You're working on **maximum/minimum subarray**, **distinct characters**, **k-size windows**, etc.

---

## 📈 Time Complexity

- Typically **O(n)** (each element is visited at most twice)
- Efficient for large input where brute force is too slow (**O(n²)**)

---

## 🧪 Common Variants

| Variant | Use Case |
|--------|----------|
| Fixed-size window | Exact window length (e.g., average of every k-length subarray) |
| Variable-size window | Expand/shrink until a condition is met (e.g., longest subarray under constraint) |
| Character counting window | Substring problems involving frequency (e.g., anagram check) |
