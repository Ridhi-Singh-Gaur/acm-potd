import java.util.*;
class Solution {
    public int evalRPN(String[] tokens) {
        Stack<Integer> s=new Stack<Integer>();
        for(int i=0;i<tokens.length;i++){
            String c=tokens[i];
            if(tokens[i].equals("+") || tokens[i].equals("-") || tokens[i].equals("*") || tokens[i].equals("/")){
                if(s.size()>=2){
                    int sec=s.pop();
                    int f=s.pop();
                    if(c.equals("+")){
                        s.push(f + sec);
                    }
                    else if(c.equals("-")){
                        s.push(f - sec);
                    }
                    else if(c.equals("/")){
                        s.push(f/sec);
                    }
                    else{
                        s.push(f * sec);
                    }
                }
            }
            else{
                s.push(Integer.parseInt(c));
            }
        }
        return s.peek();
    }
}

<img width="1918" height="1033" alt="image" src="https://github.com/user-attachments/assets/e250033f-9c7d-4e64-ba23-a1e76e06d1d0" />
