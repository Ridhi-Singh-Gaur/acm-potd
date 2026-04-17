class Solution {
    public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        if(root==null){
            return null;
        }
        if(root==p || root==q){
            return root;
        }
        TreeNode left=lowestCommonAncestor(root.left,p,q);
        TreeNode right=lowestCommonAncestor(root.right,p,q);
        if(left!=null && right!=null){
            return root;
        }
        if(left!=null){
            return left;
        }
        return right;
        /*
        ArrayList<TreeNode> h=new ArrayList<>();
        int t=calc(root,p,q,h);  
        return h.get(0);*/    
    }
    public int calc(TreeNode root, TreeNode p, TreeNode q,ArrayList<TreeNode> h){
        int c=0;
        if(root==p || root==q){
            c++;
        }
        if(root.left!=null){
            c+=calc(root.left,p,q,h);
        }
        if(root.right!=null){
           c+=calc(root.right,p,q,h);
        }
        if(c==2){
            h.add(root);
        }
        return c;
    }
}
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/2e4d0ed7-d34f-4a00-a4ac-01e6a2dba7a6" />

