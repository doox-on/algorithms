# 🧭 Binary Search Summary

## 📌 Key Concepts

- Only works on **sorted arrays**
- Time complexity: `O(log n)`
- Midpoint formula to avoid overflow: `mid = left + (right - left) / 2`

---

## [Leetcode 704. Binary Search](https://leetcode.com/problems/binary-search/description/) [2025-05-28]

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


## [Leetcode 35. Search Insert Position](https://leetcode.com/problems/search-insert-position/) [2025-05-28]

```c
int searchInsert(int* nums, int numsSize, int target) {
    int start = 0;
    int end = numsSize-1;
    int mid = 0;

    while (start <= end) {
        mid = (start + end)/2;

        if (target == nums[mid]) {
            return mid;
        } else if (target < nums[mid]) {
            end = mid - 1;
        } else {
            start = mid + 1;
        }
    }
    
    return start;

}
```

- Since the loop end condition is when start > end, the position of the start at that moment is
-  where the value is eaqual or greater than the target.
-  so if there's tatget in the array -> the target index
-  if not -> where it shold be

---

## 🧠 Common Pitfalls

- Off-by-one errors in `left = mid + 1` or `right = mid - 1`
- Forgetting to use the overflow-safe midpoint formula
- Mixing up loop conditions: `left <= right` vs `left < right`

---

## 🔍 Related LeetCode Problems

- [Leetcode 35. Search Insert Position](https://leetcode.com/problems/search-insert-position/description/) [2025-05-30]
- [Leetcode 1: Two Sum](https://leetcode.com/problems/two-sum/description/)
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
