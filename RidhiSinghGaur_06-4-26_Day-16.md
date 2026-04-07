class Solution {
    public int[] dailyTemperatures(int[] temperatures) {
        int[] a=new int[temperatures.length];
        Stack<Integer> s=new Stack<Integer>();
        for(int i=temperatures.length-1;i>=0;i--){
            if(s.isEmpty()){
                a[i]=0;
            }
            while(!s.isEmpty() && temperatures[i]>=temperatures[s.peek()]){
                s.pop();
            }
            if(s.isEmpty()){
                a[i]=0;
            }
            else{
                a[i]=Math.abs(s.peek()-i);
            }
            s.push(i);
        }
        return a;
    }
  }
  <img width="1898" height="1078" alt="image" src="https://github.com/user-attachments/assets/b43b0f8e-89c0-4df2-af6b-92866a743452" />
