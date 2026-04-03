class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        ListNode t=head;
        if(head==null){
            return null;
        }
        ListNode dummy=new ListNode(-1);
        ListNode curr=dummy;
        while(t!=null){
            if(t!=null && t.next!=null && t.next.val==t.val){
                ListNode x=t;
                t=t.next;
                while(t!=null && t.val==x.val){
                    t=t.next;
                }
            }
            else{
                curr.next=new ListNode(t.val);
                curr=curr.next;
                t=t.next;
            }
        }
        return dummy.next;
    }
}


<img width="1907" height="1078" alt="image" src="https://github.com/user-attachments/assets/1a89b052-78c2-4f10-bcae-f31e0d43aab3" />
