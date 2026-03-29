class Solution {
    public boolean checkSubarraySum(int[] nums, int k) {
        HashMap<Integer,Integer> h=new HashMap<>();
        h.put(0,-1);
        int rem=0;
        for(int i=0;i<nums.length;i++){
            rem=(rem % k + nums[i] % k) % k;
            if(h.containsKey(rem)){
                if((i-h.get(rem))>=2){
                    return true;
                }
            }else{
                h.put(rem,i);
            }
        }
        return false;
  }
}
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/ab8de3d1-be01-408b-90f0-6a5e3b37d695" />
