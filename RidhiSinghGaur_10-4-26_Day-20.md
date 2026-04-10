class Solution {
    public String removeKdigits(String num, int k) {
        int n=num.length();
        if(k>=n){
            return "0";
        }
        Stack<Character> st=new Stack<>();
        int c=0;
        for(int i=0;i<n;i++){
            char val=num.charAt(i);
            while(c<k && !st.isEmpty() && (st.peek()-'0')>(val-'0')){
                st.pop();
                c++;
            }
            st.push(val);
        }
        while(c<k){
            st.pop();
            c++;
        }
        StringBuilder sb=new StringBuilder();
        while(!st.isEmpty()){
            sb.append(st.pop());
        }
        sb.reverse();
        while(sb.length()>1 && sb.charAt(0)=='0'){
            sb.deleteCharAt(0);
        }
        return sb.toString();
    }
}

<img width="1918" height="1077" alt="image" src="https://github.com/user-attachments/assets/437cf5c2-0e9b-4fe8-a573-431fa4c817d7" />
