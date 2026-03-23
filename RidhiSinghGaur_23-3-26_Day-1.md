class Solution {
    public int firstMissingPositive(int[] nums) {
        HashSet<Integer> h=new HashSet<Integer>();
        for(int i:nums){
            if(i>=1){
                h.add(i);
            }
        }
        for(int i=1;i<Integer.MAX_VALUE;i++){
            if(!h.contains(i)){
                return i;
            }
        }
        return Integer.MAX_VALUE;
    }
}

<img width="1895" height="1078" alt="image" src="https://github.com/user-attachments/assets/ef416bee-4591-4d4a-9858-70ed9d8d03d5" />
