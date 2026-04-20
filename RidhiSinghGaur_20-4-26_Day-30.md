import java.util.*;
class Solution {
    public List<List<Integer>> combinationSum(int[] candidates, int target) {
        List<List<Integer>> ans=new ArrayList<>();
        List<Integer> l=new ArrayList<>();
        func(0,0,target,l,ans,candidates);
        return ans;
    }
    public void func(int i,int sum,int t,List<Integer> l,List<List<Integer>> ans,int[] a) {
        if(i>=a.length){
            if(sum==t){
                List<Integer> x=new ArrayList<>(l);
                ans.add(x);
            }
            return;
        }
        if(sum>t){
            return;
        }
        l.add(a[i]);
        sum+=a[i];
        func(i,sum,t,l,ans,a);
        l.remove(l.size()-1);
        sum-=a[i];
        func(i+1,sum,t,l,ans,a);
    }        
}

<img width="1905" height="1078" alt="image" src="https://github.com/user-attachments/assets/11fd50c1-b2de-4ba0-a744-5ce83df3015b" />
