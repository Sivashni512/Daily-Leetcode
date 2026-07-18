\# Merge Sorted Array



\## Problem Statement

You are given two sorted integer arrays `nums1` and `nums2`, along with integers `m` and `n`.



\- `nums1` has a size of `m + n`, where the first `m` elements contain valid values and the remaining `n` elements are set to `0`.

\- `nums2` contains `n` sorted elements.



Merge `nums2` into `nums1` so that `nums1` becomes a single sorted array.



\---



\## Approach

1\. Start inserting the elements of `nums2` into `nums1` from index `m`.

2\. Copy all elements of `nums2` into the remaining positions of `nums1`.

3\. Sort the entire `nums1` array using `Arrays.sort()`.

4\. The final sorted array is stored in `nums1`.



\---



\## Algorithm

1\. Initialize `i = m`.

2\. Traverse `nums2` using index `j`.

3\. Copy each element of `nums2` into `nums1\[i]`.

4\. Increment both `i` and `j`.

5\. After copying all elements, sort `nums1` using `Arrays.sort()`.

6\. The merged sorted array is obtained in `nums1`.



\---



\## Code



```java

class Solution {

&#x20;   public void merge(int\[] nums1, int m, int\[] nums2, int n) {

&#x20;       for (int j = 0, i = m; j < n; j++) {

&#x20;           nums1\[i] = nums2\[j];

&#x20;           i++;

&#x20;       }

&#x20;       Arrays.sort(nums1);

&#x20;   }

}

```



\---



\## Example



\### Input

```text

nums1 = \[1,2,3,0,0,0]

m = 3

nums2 = \[2,5,6]

n = 3

```



\### Output

```text

\[1,2,2,3,5,6]

```



\### Explanation

After copying the elements of `nums2` into `nums1`, the array becomes:



```text

\[1,2,3,2,5,6]

```



After sorting:



```text

\[1,2,2,3,5,6]

```



\---



\## Complexity Analysis



\- \*\*Time Complexity:\*\* `O((m + n) log(m + n))`

\- \*\*Space Complexity:\*\* `O(1)`



\---



\## Key Features

\- Simple and easy to implement.

\- Uses Java's built-in `Arrays.sort()` method.

\- Produces the correct merged sorted array.

\- Suitable for beginners learning array manipulation.

