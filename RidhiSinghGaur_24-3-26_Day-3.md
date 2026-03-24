class Solution {
    public void sortColors(int[] nums) {
        int zero=0;
        int one=0;
        int two=0;
        for(int i:nums){
            if(i==0){
                zero++;
            }else if(i==1){
                one++;
            }else{
                two++;
            }
        }
        int idx=0;
        for(int i=0;i<zero;i++){
            nums[idx++]=0;
        }
        for(int i=0;i<one;i++){
            nums[idx++]=1;
        }
        for(int i=0;i<two;i++){
            nums[idx++]=2;
        }
    }
}

<img width="1918" height="1062" alt="image" src="https://github.com/user-attachments/assets/b440cb4a-88fa-4925-ab83-9342f47969ef" />
