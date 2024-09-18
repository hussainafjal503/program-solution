# 61. Rotate List

Given the head of a linked list, rotate the list to the right by k places.

 
Example 1:

Input: head = [1,2,3,4,5], k = 2
Output: [4,5,1,2,3]

Example 2:

Input: head = [0,1,2], k = 4
Output: [2,0,1]

Constraints:

    The number of nodes in the list is in the range [0, 500].
    -100 <= Node.val <= 100
    0 <= k <= 2 * 109


# Java
```java

class Solution {
    int getLength(ListNode head){
        int len=0;
        while(head!=null){
            len++;
            head=head.next;
        }
        return len;
    }
    public ListNode rotateRight(ListNode head, int k) {
        if(head==null)
            return null;
        
        int len=getLength(head);
        int actualLength=(k%len);

        if(actualLength==0)
            return head;
        
        int newLastpos=len-actualLength-1;

        ListNode newHead=null;

        ListNode newtail=head;

        for(int i=0;i<newLastpos;i++){
            newtail=newtail.next;
        }

        newHead=newtail.next;
        newtail.next=null;

        ListNode it=newHead;
        while(it.next!=null){
            it=it.next;
        }

        it.next=head;
        return newHead;
    }
}
```
