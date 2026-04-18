class Solution {
    public boolean isSubtree(TreeNode root, TreeNode subRoot) {
        if(checkEqual(root,subRoot)){
            return true;
        }
        if(root!=null && isSubtree(root.left,subRoot)){
            return true;
        }
        if(root!=null && isSubtree(root.right,subRoot)){
            return true;
        }
        return false;
    }
    public boolean checkEqual(TreeNode root,TreeNode subRoot){
        if((root==null && subRoot!=null) || (root!=null && subRoot==null)){
            return false;
        }
        if(root==null && subRoot==null){
            return true;
        }
        if(root.val!=subRoot.val){
            return false;
        }
        return checkEqual(root.left,subRoot.left) && checkEqual(root.right,subRoot.right);
    }
}

<img width="1915" height="1077" alt="image" src="https://github.com/user-attachments/assets/77a724f0-8652-4be2-8b77-1f2f5c78edab" />
