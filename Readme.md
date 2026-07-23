\# 🎨 Sort Colors



\## 📌 Problem Statement

Given an array `nums` containing only `0`, `1`, and `2`, sort the array in-place so that objects of the same color are adjacent, with the colors in the order \*\*0 (Red), 1 (White), and 2 (Blue)\*\*.



You must solve the problem \*\*without using the library's sort function\*\*.



\### Example

\*\*Input:\*\*

```text

nums = \[2,0,2,1,1,0]

```



\*\*Output:\*\*

```text

\[0,0,1,1,2,2]

```



\---



\## 💡 Approach

This solution uses the \*\*Dutch National Flag Algorithm\*\*, which sorts the array in a single traversal.



Three pointers are maintained:



\- \*\*low\*\* → Position where the next `0` should be placed.

\- \*\*mid\*\* → Current element being checked.

\- \*\*high\*\* → Position where the next `2` should be placed.



\### Steps:

1\. Initialize `low = 0`, `mid = 0`, and `high = n - 1`.

2\. Traverse the array while `mid <= high`.

3\. If the current element is:

&#x20;  - \*\*0\*\* → Swap with `low`, then increment both `low` and `mid`.

&#x20;  - \*\*1\*\* → Leave it in place and increment `mid`.

&#x20;  - \*\*2\*\* → Swap with `high` and decrement `high` (do not increment `mid` because the swapped element needs to be checked).

4\. Continue until all elements are sorted.



\---



\## ✅ Algorithm

1\. Set three pointers: `low`, `mid`, and `high`.

2\. While `mid <= high`:

&#x20;  - If `nums\[mid] == 0`

&#x20;    - Swap `nums\[low]` and `nums\[mid]`

&#x20;    - Increment `low` and `mid`

&#x20;  - Else if `nums\[mid] == 1`

&#x20;    - Increment `mid`

&#x20;  - Else (`nums\[mid] == 2`)

&#x20;    - Swap `nums\[mid]` and `nums\[high]`

&#x20;    - Decrement `high`

3\. Return the sorted array.



\---



\## ⏱️ Complexity Analysis



\- \*\*Time Complexity:\*\* `O(n)`

&#x20; - The array is traversed only once.



\- \*\*Space Complexity:\*\* `O(1)`

&#x20; - Sorting is done in-place without using extra space.



\---



\## 🚀 Key Concepts

\- Dutch National Flag Algorithm

\- Two/Three Pointer Technique

\- In-place Sorting

\- Array Manipulation



\---



\## ✅ Java Solution



```java

class Solution {

&#x20;   public void sortColors(int\[] nums) {

&#x20;       int n = nums.length;

&#x20;       int low = 0, mid = 0, high = n - 1;



&#x20;       while (mid <= high) {

&#x20;           if (nums\[mid] == 0) {

&#x20;               int t = nums\[low];

&#x20;               nums\[low] = nums\[mid];

&#x20;               nums\[mid] = t;

&#x20;               low++;

&#x20;               mid++;

&#x20;           } else if (nums\[mid] == 1) {

&#x20;               mid++;

&#x20;           } else {

&#x20;               int t = nums\[high];

&#x20;               nums\[high] = nums\[mid];

&#x20;               nums\[mid] = t;

&#x20;               high--;

&#x20;           }

&#x20;       }

&#x20;   }

}

```



\---



\## 🎯 Result

The array is sorted \*\*in-place\*\* in a single pass using the \*\*Dutch National Flag Algorithm\*\*, achieving \*\*O(n)\*\* time complexity and \*\*O(1)\*\* extra space.

