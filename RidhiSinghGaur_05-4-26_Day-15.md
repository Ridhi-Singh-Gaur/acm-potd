class Solution {
    public ListNode swapPairs(ListNode head) {
        if(head==null){
            return null;
        }
        if(length(head)<=1){
            return head;
        }
        if(length(head)%2==0){
            head=swap(length(head)-1,head);
            return head;
        }
        head=swap(length(head)-2,head);
        return  head;
    }
    public ListNode swap(int length,ListNode head){
        ListNode n=head;
        int i=0;
        while(i<=length/2){
           int t=n.val;
           n.val=n.next.val;
           n.next.val=t;
           i++;
           n=n.next.next;
        }
        return head;
    }
    public int length(ListNode head){
        int l=1;
        ListNode t=head;
        while(t.next!=null){
            t=t.next;
            l++;
        }
        return l;
    }
}

<img width="1918" height="1077" alt="image" src="https://github.com/user-attachments/assets/81c3e235-ec5f-4049-a85f-da173abc0b10" />
