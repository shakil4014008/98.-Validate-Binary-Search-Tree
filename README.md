# 98.-Validate-Binary-Search-Tree

`````py
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isValidBST(self, root: Optional[TreeNode]) -> bool:

        min = float('-inf')
        max = float('inf')
        def is_valid_bst(root, min, max):
            if root is None: return True # need base case 
            if min >= root.val or max <= root.val: return False 
            return is_valid_bst(root.left, min, root.val) and \
                    is_valid_bst(root.right, root.val, max)

        return is_valid_bst(root, min, max)


````
