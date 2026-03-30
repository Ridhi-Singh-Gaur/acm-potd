public class Solution {
    public ListNode detectCycle(ListNode head) {
        ListNode ans;
        ListNode f=head;
        ListNode s=head;
        while(f!=null && f.next!=null){
            s=s.next;
            f=f.next.next;
            if(s==f){
                break;
            }
        }
        if(s==f){
            ListNode t=head;
            HashMap<ListNode,Integer> h=new HashMap<>();
            while(t!=null){
                ans=t;
                int freq=0;
                if(h.containsKey(ans)){
                    freq=h.get(ans);
                }
                freq++;
                h.put(ans,freq);
                if(freq==2){
                    return ans;
                }
                t=t.next;
            }
        }
        ans=new ListNode(-1);
        return null;
    }
}
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/e5ec41dd-dee9-4635-bd9e-41a5fadbd7e6" />
