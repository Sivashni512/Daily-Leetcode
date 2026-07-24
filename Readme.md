# Build Array from Permutation

## 📝 Problem Statement

Given a zero-based permutation `nums`, build an array `ans` of the same length where:

`ans[i] = nums[nums[i]]`

Return the resulting array.

---

## 💡 Approach

* Create a new array `arr1` with the same length as `nums`.
* Traverse the array using a loop.
* Store the value `nums[nums[i]]` at each index in `arr1`.
* Return the newly created array.

---

## 🚀 Algorithm

1. Create an array `arr1` of size `nums.length`.
2. Iterate through the array from `0` to `nums.length - 1`.
3. Assign `arr1[i] = nums[nums[i]]`.
4. Return `arr1`.

---

## ⏱️ Complexity Analysis

* **Time Complexity:** `O(n)`
* **Space Complexity:** `O(n)`

---

## ✅ Java Code

```java
class Solution {
    public int[] buildArray(int[] nums) {
        int[] arr1 = new int[nums.length];
        for (int i = 0; i < nums.length; i++) {
            arr1[i] = nums[nums[i]];
        }
        return arr1;
    }
}
```

---

## 📚 Concepts Used

* Arrays
* Permutation
* Index Mapping
* Iteration
