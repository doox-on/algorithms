# 🧭 Binary Search Summary

## 📌 Key Concepts

- Only works on **sorted arrays**
- Time complexity: `O(log n)`
- Midpoint formula to avoid overflow: `mid = left + (right - left) / 2`

---

## 🔁 Iterative Version (while left <= right)

```c
int binarySearch(int* arr, int size, int target) {
    int left = 0, right = size - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return -1;
}
```

---

## 🧠 Common Pitfalls

- Off-by-one errors in `left = mid + 1` or `right = mid - 1`
- Forgetting to use the overflow-safe midpoint formula
- Mixing up loop conditions: `left <= right` vs `left < right`

---

## 🔍 Related LeetCode Problems

- Leetcode 704: Binary Search
- Leetcode 35: Search Insert Position
- Leetcode 278: First Bad Version

---

## 🤔 Interview Checklist

- [ ] Can you implement both iterative and recursive versions?
- [ ] Can you explain upper vs. lower bound binary search?
- [ ] Can you apply binary search to custom conditions (e.g., `isBadVersion`)?

---

## 🧪 Personal Notes

- Initially confused about when to update `left` and `right`
- Forgot to handle `left == right` edge case correctly
- Mixed up logic when `arr[mid] == target`
