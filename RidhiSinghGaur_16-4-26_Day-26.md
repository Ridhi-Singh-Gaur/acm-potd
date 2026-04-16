class Solution {
    public int kthSmallest(TreeNode root, int k) {
        ArrayList<Integer> l=new ArrayList<>();
        preOrder(root,l);
        return l.get(k-1);
    }
    public void preOrder(TreeNode root,ArrayList<Integer> l){
        if(root==null){
            return;
        }
        preOrder(root.left,l);
        l.add(root.val);   
        preOrder(root.right,l);    
    }
}

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/38bbafe4-2165-4767-a4ea-568c37f03c40" />
