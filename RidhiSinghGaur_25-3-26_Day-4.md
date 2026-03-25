class Solution {
    public int[] twoSum(int[] a, int t) {
        int[] x=new int[2];
        int i=0;
        int j=a.length-1;
        while(i<=j && (a[i]+a[j])!=t){
            if((a[i]+a[j])>t){
                j--;
            }
            else{
                i++;
            }
        }
        x[0]=i+1;
        x[1]=j+1;
        return x;
  }
}
<img width="1918" height="1068" alt="image" src="https://github.com/user-attachments/assets/0dc13d72-fa90-4f52-b159-81aefa6c0c56" />
