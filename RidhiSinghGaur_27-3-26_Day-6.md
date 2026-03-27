class Solution {
    public boolean increasingTriplet(int[] nums) {
        int[] min=new int[nums.length];
        int[] max=new int[nums.length];
        max[max.length-1]=nums.length-1;
        min[0]=0;
        for(int i=1;i<nums.length;i++){
            int index=min[i-1];
            if(nums[i]<nums[index]){
                index=i;
            }
            min[i]=index;
        }
        for(int i=nums.length-2;i>=0;i--){
            int index=max[i+1];
            if(nums[i]>nums[index]){
                index=i;
            }
            max[i]=index;
        }
        for(int i=1;i<nums.length-1;i++){
            if(nums[min[i-1]]<nums[i] && nums[i]<nums[max[i+1]]){
                return true;
            }
        }
        return false;
    }
}
<img width="1918" height="1072" alt="image" src="https://github.com/user-attachments/assets/579203a4-4e5c-4fd4-a6f0-98e25ba4762c" />
