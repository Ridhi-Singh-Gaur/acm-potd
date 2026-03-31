class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummy=new ListNode();
        ListNode t=dummy;
        ListNode t1=l1;
        ListNode t2=l2;
        int carry=0;
        while(t1!=null || t2!=null || carry==1){
            int sum=0;
            if(t1!=null){
                sum+=t1.val;
                t1=t1.next;
            }
            if(t2!=null){
                sum+=t2.val;
                t2=t2.next;
            } 
            sum+=carry;
            carry=sum/10;
            t.next=new ListNode(sum%10);
            t=t.next;           
        }
        dummy=dummy.next;
        return dummy;
  }
}
<img width="1890" height="1078" alt="image" src="https://github.com/user-attachments/assets/ae39ee6e-a815-48d9-ad8c-c9622c2ea6d6" />

