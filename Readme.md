# Binary Search in Java

## Problem Statement

Given a sorted array of integers `nums` and an integer `target`, return the index of `target` if it exists in the array. Otherwise, return `-1`.

This solution uses the **Binary Search** algorithm, which efficiently searches a sorted array by repeatedly dividing the search interval in half.

---

## Algorithm

1. Initialize two pointers:
   - `left = 0`
   - `right = nums.length - 1`
2. Repeat while `left <= right`:
   - Find the middle index.
   - If the middle element equals the target, return its index.
   - If the target is greater than the middle element, search the right half.
   - Otherwise, search the left half.
3. If the target is not found, return `-1`.

---

## Java Code

```java
class Solution {
    public int search(int[] nums, int target) {
        int left = 0;
        int right = nums.length - 1;

        while (left <= right) {
            int mid = left + (right - left) / 2;

            if (nums[mid] == target) {
                return mid;
            } else if (nums[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }

        return -1;
    }
}
```

---

## Example

### Input

```text
nums = [-1,0,3,5,9,12]
target = 9
```

### Output

```text
4
```

### Explanation

The target value `9` is found at index `4`.

---

## Time Complexity

- **Best Case:** O(1)
- **Average Case:** O(log n)
- **Worst Case:** O(log n)

---

## Space Complexity

- **O(1)** (Constant extra space)

---

## Features

- Efficient search using Binary Search.
- Constant space usage.
- Handles large sorted arrays efficiently.
- Returns `-1` when the target element is not present.

---

## Requirements

- Java 8 or later
- Input array must be sorted in ascending order.

---

## Author

**Sivashni S**