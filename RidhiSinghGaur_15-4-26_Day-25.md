class Solution {
    public List<List<Integer>> levelOrder(TreeNode root) {
        List<List<Integer>> li=new ArrayList<>();
        if(root==null){
            return li;
        }
        Queue<TreeNode> q=new LinkedList<>();
        q.add(root);
        while(!q.isEmpty()){
            int n=q.size();
            List<Integer> l=new ArrayList<>();
            for(int i=0;i<n;i++){
                TreeNode t=q.remove();
                if(t!=null){
                    l.add(t.val);
                    if(t.left!=null){
                        q.add(t.left);
                    }
                    if(t.right!=null){
                        q.add(t.right);
                    }
                }
            }
            li.add(l);
        }
        return li;
    }
}

<img width="1860" height="1002" alt="image" src="https://github.com/user-attachments/assets/957e6c47-9494-43a7-855e-884939dbbddb" />
