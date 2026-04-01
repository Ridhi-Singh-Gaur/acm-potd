import  java.util.*;
class Solution {
    public ListNode sortList(ListNode head) {
        if(head==null || head.next==null){
            return head;
        }
        ArrayList<Integer> a=new ArrayList<Integer>();
        ListNode t=head;
        while(t!=null){
            a.add(t.val);
            t=t.next;
        } 
        Collections.sort(a);
        ListNode ans=new ListNode(a.get(0)); 
        t=ans;
        for(int i=1;i<a.size();i++){
            t.next=new ListNode(a.get(i));
            t=t.next;
        }   
        return ans;
    }
}

<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/bac8f91f-edcf-423f-b6b7-5e4b8b7ba089" />
