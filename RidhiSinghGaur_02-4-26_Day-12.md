class Solution {
    public ListNode rotateRight(ListNode head, int k) {
        if(head==null){
            return null;
        }
        ListNode t=head;
        int c=0;
        while(t!=null){
            t=t.next;
            c++;
        }
        if(k%c==0){
            return head;
        }
        k=k%c;
        t=head;
        ListNode last=head;
        int i=0;
        while(i<c-k){//i<2
            last=last.next;
            i++;
        }
        i=0;
        t=head;
        while(i<(c-k)){
            if(i==c-k-1){
                t.next=null;
                break;
            }
            t=t.next;
            i++;
        }
        ListNode n=last;
        while(n.next!=null){
            n=n.next;
        }
        n.next=head;
        return last;
    }    
}
<img width="1918" height="1078" alt="image" src="https://github.com/user-attachments/assets/dead3755-2b75-430d-b5c0-a396e93318bf" />
