import java.util.*;
class Solution {
    public int[] nextGreaterElements(int[] nums) {
        int[] a=new int[nums.length];
        Arrays.fill(a,-1);
        Stack<Integer> s=new Stack<Integer>();
        for(int i=2*nums.length-1;i>=0;i--){
            int ind=i % nums.length;
            while(!s.isEmpty() && nums[ind]>=s.peek()){
                s.pop();
            }
            if(!s.isEmpty() && a[ind]==-1){
                a[ind]=s.peek();
            }
            s.push(nums[ind]);
        }
        return a;
    }
  }
<img width="1918" height="1077" alt="image" src="https://github.com/user-attachments/assets/53be7090-f810-45e8-bc60-93f81b5e9c08" />
