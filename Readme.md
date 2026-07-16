\# Construct Binary Tree from Preorder and Inorder Traversal



\## Problem Statement

Given two integer arrays:



\- `preorder` – preorder traversal of a binary tree.

\- `inorder` – inorder traversal of the same binary tree.



Construct and return the binary tree.



\---



\## Approach



The solution uses \*\*Recursion\*\* along with a \*\*HashMap\*\* for efficient lookup.



\### Algorithm



1\. Store each value of the inorder traversal along with its index in a `HashMap`.

2\. Maintain a global variable `index` to track the current root in the preorder array.

3\. The first element in preorder is always the root.

4\. Find the root's position in the inorder array using the HashMap.

5\. Recursively build:

&#x20;  - Left subtree using the left portion of inorder.

&#x20;  - Right subtree using the right portion of inorder.

6\. Continue until the subtree boundaries become invalid.



\---



\## Code



```java

class Solution {

&#x20;   int index = 0;



&#x20;   public TreeNode buildTree(int\[] preorder, int\[] inorder) {

&#x20;       HashMap<Integer, Integer> map = new HashMap<>();



&#x20;       for (int i = 0; i < inorder.length; i++) {

&#x20;           map.put(inorder\[i], i);

&#x20;       }



&#x20;       return helper(preorder, 0, inorder.length - 1, map);

&#x20;   }



&#x20;   private TreeNode helper(int\[] preorder, int start, int end, HashMap<Integer, Integer> map) {

&#x20;       if (start > end)

&#x20;           return null;



&#x20;       int rootVal = preorder\[index++];

&#x20;       TreeNode node = new TreeNode(rootVal);



&#x20;       int inorderIndex = map.get(rootVal);



&#x20;       node.left = helper(preorder, start, inorderIndex - 1, map);

&#x20;       node.right = helper(preorder, inorderIndex + 1, end, map);



&#x20;       return node;

&#x20;   }

}

```



\---



\## Dry Run



\### Input



```text

preorder = \[3,9,20,15,7]

inorder  = \[9,3,15,20,7]

```



\### Construction



```

Root = 3



Left Subtree:

9



Right Subtree:

20

├──15

└──7

```



\### Output



```

&#x20;       3

&#x20;      / \\

&#x20;     9   20

&#x20;        /  \\

&#x20;       15   7

```



\---



\## Time Complexity



\- Building HashMap: \*\*O(n)\*\*

\- Constructing Tree: \*\*O(n)\*\*



\*\*Overall Time Complexity:\*\* \*\*O(n)\*\*



\---



\## Space Complexity



\- HashMap: \*\*O(n)\*\*

\- Recursive Call Stack: \*\*O(n)\*\* (worst case)



\*\*Overall Space Complexity:\*\* \*\*O(n)\*\*



\---



\## Key Concepts



\- Binary Tree

\- Preorder Traversal

\- Inorder Traversal

\- Recursion

\- Divide and Conquer

\- HashMap



\---



\## Explanation



\- \*\*Preorder Traversal\*\* always gives the root first.

\- \*\*Inorder Traversal\*\* divides the tree into left and right subtrees.

\- The HashMap allows locating the root in constant time.

\- Recursion builds the left subtree first, then the right subtree, following preorder traversal.



\---



\## Example



\*\*Input\*\*



```

preorder = \[1,2,4,5,3]

inorder  = \[4,2,5,1,3]

```



\*\*Output\*\*



```

&#x20;       1

&#x20;      / \\

&#x20;     2   3

&#x20;    / \\

&#x20;   4   5

```



\---



\## Topics



\- Trees

\- Binary Tree

\- Recursion

\- HashMap

\- Divide and Conquer

\- LeetCode 105

