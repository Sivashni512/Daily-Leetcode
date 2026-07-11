# 🧩 Two Sum Problem (Java)

## 📖 Problem Statement
Given an array of integers `nums` and an integer `target`, return the indices of the two numbers such that they add up to `target`.

- Each input has exactly one solution.
- You may not use the same element twice.
- The answer can be returned in any order.

---

## 💻 Solution Approach
This implementation uses a **brute force method**:
- Iterate through all pairs of numbers.
- Check if their sum equals the target.
- Return the indices if found.

### Code
```java
class TwoSum {
    public int[] twoSum(int[] nums, int target) {
        int n = nums.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = i + 1; j < n; j++) {
                if (nums[i] + nums[j] == target) {
                    return new int[]{i, j};
                }
            }
        }
        return new int[]{}; // No solution found
    }
}

