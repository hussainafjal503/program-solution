# 25. Reverse Nodes in k-Group

Given the head of a linked list, reverse the nodes of the list k at a time, and return the modified list.

k is a positive integer and is less than or equal to the length of the linked list. If the number of nodes is not a multiple of k then left-out nodes, in the end, should remain as it is.

You may not alter the values in the list's nodes, only nodes themselves may be changed.


Example 1:

Input: head = [1,2,3,4,5], k = 2
Output: [2,1,4,3,5]

Example 2:

Input: head = [1,2,3,4,5], k = 3
Output: [3,2,1,4,5]


Constraints:

    The number of nodes in the list is n.
    1 <= k <= n <= 5000
    0 <= Node.val <= 1000

 

Follow-up: Can you solve the problem in O(1) extra memory space?

# Java
```
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public int getLen(ListNode head){
        int count=0;
        ListNode it=head;
        while(it!=null){
            count++;
            it=it.next;
        }
        return count;
    }
    public ListNode reverseKGroup(ListNode head, int k) {
        if(head==null)
            return null;
        
        int n=getLen(head);
        if(k>n)
            return head;
        
        ListNode prev=null;
        ListNode curr=head;
        ListNode forward=null;

        int count=0;
        while(count<k){
            forward=curr.next;
            curr.next=prev;
            prev=curr;
            curr=forward;
            count++;
           
        }

        if(forward!=null)
            head.next=reverseKGroup(forward,k);
        return prev;
        
    }
}
```
