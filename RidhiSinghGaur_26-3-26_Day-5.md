class Solution {
    public int[] productExceptSelf(int[] nums) {
        int[] ans=new int[nums.length];
        int[] after=new int[nums.length];
        after[nums.length-1]=1;
        for(int i=nums.length-2;i>=0;i--){
            after[i]=after[i+1]*nums[i+1];
        }
        int prev=1;
        ans[0]=after[0];
        for(int i=1;i<nums.length;i++){
            prev=nums[i-1]*prev;
            ans[i]=prev*after[i];
        }
        return ans;
    }
}
<img width="1916" height="1077" alt="image" src="https://github.com/user-attachments/assets/7ff58f36-f355-414f-8885-3af781ac477b" />
