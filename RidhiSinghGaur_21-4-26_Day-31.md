import java.util.*;
class Solution {//)
    public List<String> generateParenthesis(int n) {
        List<String> l=new ArrayList<String>();
        StringBuffer s=new StringBuffer();
        paren(n,0,0,l,s);
        return l;
    }
    public void paren(int n,int open,int close,List<String> l, StringBuffer s){
        if(close>open){
            return ;
        }
        if(open>n){
            return;
        }
        if(open==close && open==n){
            l.add(s.toString());
            return;
        }
        if(open>=close){
            s.append("(");
            paren(n,open+1,close,l,s);
            s.deleteCharAt(s.length()-1);
            s.append(")");
            paren(n,open,close+1,l,s);
            s.deleteCharAt(s.length()-1);
        }
    }
}

<img width="1906" height="1078" alt="image" src="https://github.com/user-attachments/assets/214dfbd5-02cf-4075-a0a0-0c6e8cfca512" />
