class Solution {
    public ListNode removeNthFromEnd(ListNode head, int k) {
        if(head==null || (head.next==null && k==1)){
            return null;
        }
        ListNode slow=head;
        ListNode fast=head;
        int i=0;
        while(i<k){
            fast=fast.next;
            i++;
        }
        if(fast==null){
            head=head.next;
            return head;
        }
        while(fast.next!=null){
            fast=fast.next;
            slow=slow.next;
        }
        if(slow.next!=null){
            slow.next=slow.next.next;
        }
        return head;
  }
}
<img width="1913" height="1076" alt="image" src="https://github.com/user-attachments/assets/d6c6aed4-bc10-4274-baac-d9eeac27a390" />
