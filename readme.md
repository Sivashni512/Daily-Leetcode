\# Running Sum of 1D Array



\## 📝 Problem Statement

Given an array `nums`, return the \*\*running sum\*\* of the array.



The running sum of an array is defined as:



runningSum\[i] = nums\[0] + nums\[1] + ... + nums\[i]



\---



\## 💡 Approach



\- Start iterating from the second element of the array.

\- Add the previous element (which already stores the running sum) to the current element.

\- Update the current element with this new value.

\- Continue until the end of the array.

\- Return the modified array.



\---



\## 🚀 Algorithm



1\. Traverse the array from index `1` to `nums.length - 1`.

2\. Update each element using:

&#x20;  ```java

&#x20;  nums\[i] += nums\[i - 1];

&#x20;  ```

3\. Return the updated array.



\---



\## 💻 Java Code



```java

class Solution {

&#x20;   public int\[] runningSum(int\[] nums) {

&#x20;       for (int i = 1; i < nums.length; i++) {

&#x20;           nums\[i] += nums\[i - 1];

&#x20;       }

&#x20;       return nums;

&#x20;   }

}

```



\---



\## ⏱️ Complexity Analysis



\- \*\*Time Complexity:\*\* `O(n)`

\- \*\*Space Complexity:\*\* `O(1)`



\---



\## ✅ Example



\*\*Input:\*\*

```text

nums = \[1,2,3,4]

```



\*\*Output:\*\*

```text

\[1,3,6,10]

```



\*\*Explanation:\*\*



\- Running Sum at index 0 = 1

\- Running Sum at index 1 = 1 + 2 = 3

\- Running Sum at index 2 = 1 + 2 + 3 = 6

\- Running Sum at index 3 = 1 + 2 + 3 + 4 = 10



\---



\## 📚 Concepts Used



\- Array

\- Prefix Sum

\- Iteration

\- In-place Array Update

