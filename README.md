# 98.-Validate-Binary-Search-Tree

`````c#

Given a binary tree, determine if it is a valid binary search tree (BST).

Assume a BST is defined as follows:

The left subtree of a node contains only nodes with keys less than the node's key.
The right subtree of a node contains only nodes with keys greater than the node's key.
Both the left and right subtrees must also be binary search trees.


/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     public int val;
 *     public TreeNode left;
 *     public TreeNode right;
 *     public TreeNode(int val=0, TreeNode left=null, TreeNode right=null) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
 
 // Here min and max is replaced in the argument based on BST property and used polymorphism in calling function
public class Solution {    
    
    public bool IsValidBST(TreeNode root) {
        return IsValidBST(root, long.MinValue, long.MaxValue); 
    }
    
    public bool IsValidBST(TreeNode root, long min, long max){
        
        if(root == null) return true;
        
        if(min >= root.val || max <= root.val) return false;
        
        return IsValidBST(root.left, min, root.val) &&
                IsValidBST(root.right, root.val, max);
    }
}
````
