# 148. Sort List

Given the head of a linked list, return the list after sorting it in ascending order.

 

Example 1:

Input: head = [4,2,1,3]
Output: [1,2,3,4]

Example 2:

Input: head = [-1,5,3,4,0]
Output: [-1,0,3,4,5]

Example 3:

Input: head = []
Output: []

 

Constraints:

    The number of nodes in the list is in the range [0, 5 * 104].
    -105 <= Node.val <= 105

 

Follow up: Can you sort the linked list in O(n logn) time and O(1) memory (i.e. constant space)?

# Java
```java
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
    public ListNode sortList(ListNode head) {
        if(head==null || head.next==null)
            return head;
        
        ListNode mid=findMid(head);

        ListNode left=head;
        ListNode right=mid.next;

        mid.next=null;

        left = sortList(left);
        right = sortList(right);

        //merging ll

        ListNode mergeLL= merge(left,right);
        return mergeLL;
    }


    public ListNode findMid(ListNode head){
        ListNode slow=head;
        ListNode fast=head.next;
        while(fast!=null){
            fast=fast.next;
            if(fast!=null){
                fast=fast.next;
                slow=slow.next;
            }
        }
        return slow;
    }

    public ListNode merge(ListNode left, ListNode right){
        if(left==null)
            return right;
        if(right==null)
            return left;
        
        ListNode ans=new ListNode(-1);
        ListNode mptr=ans;

        while(left!=null && right!=null){
            if(left.val<=right.val){
                mptr.next=left;
                mptr=left;
                left=left.next;
            }
            else{
                mptr.next=right;
                mptr=right;
                right=right.next;
            }
        }

        if(left!=null)
            mptr.next=left;
        if(right!=null)
            mptr.next=right;
        
        ans=ans.next;
        return ans;
    }
}
```
