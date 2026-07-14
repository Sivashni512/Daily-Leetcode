// Definition for a binary tree node

class TreeNode {

&#x20;   int val;

&#x20;   TreeNode left;

&#x20;   TreeNode right;



&#x20;   TreeNode() {}

&#x20;   TreeNode(int val) { this.val = val; }

&#x20;   TreeNode(int val, TreeNode left, TreeNode right) {

&#x20;       this.val = val;

&#x20;       this.left = left;

&#x20;       this.right = right;

&#x20;   }

}



class Solution {

&#x20;   public int maxDepth(TreeNode root) {

&#x20;       if (root == null) {

&#x20;           return 0;

&#x20;       }

&#x20;       

&#x20;       int leftDepth = maxDepth(root.left);

&#x20;       int rightDepth = maxDepth(root.right);

&#x20;       

&#x20;       return 1 + Math.max(leftDepth, rightDepth);

&#x20;   }

}



// Driver code to test

public class Main {

&#x20;   public static void main(String\[] args) {

&#x20;       // Build sample tree:

&#x20;       //       3

&#x20;       //      / \\

&#x20;       //     9  20

&#x20;       //        / \\

&#x20;       //       15  7

&#x20;       TreeNode root = new TreeNode(3);

&#x20;       root.left = new TreeNode(9);

&#x20;       root.right = new TreeNode(20, new TreeNode(15), new TreeNode(7));



&#x20;       Solution sol = new Solution();

&#x20;       System.out.println("Maximum Depth: " + sol.maxDepth(root)); // Output: 3

&#x20;   }

}



