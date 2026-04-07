import java.util.*;
class Solution {
    public int[] nextGreaterElement(int[] nums1, int[] nums2) {
        int[] ans=new int[nums1.length];
        Stack<Integer> s;
        for(int i=0;i<nums1.length;i++){
            s=new Stack<>();
            for(int j=0;j<nums2.length;j++){
                s.push(nums2[j]);
            }
            int a=-1;
            int j=s.size()-1;
            while(s.isEmpty()==false && nums2[j]!=nums1[i]){
                int k=s.pop();
                if(k>nums1[i]){
                    a=k;
                }
                j--;
            }
            ans[i]=a;
        }
        return ans;
    } 
  }
}
<img width="1918" height="1053" alt="image" src="https://github.com/user-attachments/assets/96f886c3-1f43-4486-8ddd-b3ff421e88c2" />
