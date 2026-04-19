class Solution {
    public List<List<Integer>> subsets(int[] nums) {
        List<List<Integer>> l=new ArrayList<>();
        List<Integer> x=new ArrayList<>();
        powerset(l,nums,x,0);
        return l;
    }
    public void powerset(List<List<Integer>> l,int[] a,List<Integer> k,int index){
        if(index==a.length){
            l.add(new ArrayList<>(k));
            return;
        }
        k.add(a[index]);
        powerset(l,a,k,index+1);
        k.remove(k.size()-1);
        powerset(l,a,k,index+1);
    }
}

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/90355885-6f3c-4fe5-a391-b5753dfc1739" />
