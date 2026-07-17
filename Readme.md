\# Concatenation of Array



\## Problem Statement

Given an integer array `nums` of length `n`, create a new array `ans` of length `2n` where:



\- `ans\[i] = nums\[i]`

\- `ans\[i + n] = nums\[i]`



for `0 <= i < n`.



Return the concatenated array.



\### Example



\*\*Input:\*\*

```

nums = \[1,2,1]

```



\*\*Output:\*\*

```

\[1,2,1,1,2,1]

```



\---



\## Approach



1\. Find the length of the input array.

2\. Create a new array of size `2 × length`.

3\. Traverse the original array once.

4\. Copy each element:

&#x20;  - First into the same index.

&#x20;  - Again into the index `i + length`.

5\. Return the new array.



\---



\## Algorithm



1\. Store the length of `nums`.

2\. Create an integer array `ans` of size `2 \* length`.

3\. Loop through the original array.

4\. Assign:

&#x20;  - `ans\[i] = nums\[i]`

&#x20;  - `ans\[i + length] = nums\[i]`

5\. Return `ans`.



\---



\## Code



```java

class Solution {

&#x20;   public int\[] getConcatenation(int\[] nums) {

&#x20;       int len = nums.length;

&#x20;       int\[] ans = new int\[2 \* len];



&#x20;       for (int i = 0; i < len; i++) {

&#x20;           ans\[i] = nums\[i];

&#x20;           ans\[i + len] = nums\[i];

&#x20;       }



&#x20;       return ans;

&#x20;   }

}

```



\---



\## Time Complexity



\- \*\*O(n)\*\*



The array is traversed only once.



\---



\## Space Complexity



\- \*\*O(n)\*\*



A new array of size `2n` is created.



\---



\## Key Concepts



\- Arrays

\- Iteration

\- Index Manipulation



\---



\## LeetCode



\*\*Problem:\*\* 1929 - Concatenation of Array



\*\*Difficulty:\*\* Easy

