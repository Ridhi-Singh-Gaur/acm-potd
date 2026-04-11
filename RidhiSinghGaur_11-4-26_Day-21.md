class Solution {
    public boolean find132pattern(int[] nums) {
        int nums3=Integer.MIN_VALUE;
        Stack<Integer> s=new Stack<>();
        for(int i=nums.length-1;i>=0;i--){
            if(nums[i]<nums3){
                return true;
            }
            while(!s.isEmpty() && nums[i]>s.peek()){
                nums3=s.pop();
            }
            s.push(nums[i]);
        }
        return false;
    }
  }
  <img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/49a7d432-1756-40e6-9ff0-e4259c1bba67" />
