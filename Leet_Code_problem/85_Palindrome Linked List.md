# 234. Palindrome Linked List

Given the head of a singly linked list, return true if it is a
palindrome
or false otherwise.

 

Example 1:

Input: head = [1,2,2,1]
Output: true

Example 2:

Input: head = [1,2]
Output: false

Constraints:

    The number of nodes in the list is in the range [1, 105].
    0 <= Node.val <= 9

 
Follow up: Could you do it in O(n) time and O(1) space?

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

    public ListNode findmiddle(ListNode head){
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
    public ListNode reverse(ListNode head){
        ListNode prev=null;
        ListNode curr=head;
        ListNode forward=null;
        while(curr!=null){
            forward=curr.next;
            curr.next=prev;
            prev=curr;
            curr=forward;
        }
        return prev;
    }
    public boolean isPalindrome(ListNode head) {
        if(head==null || head.next==null)
            return true;

        ListNode mid=findmiddle(head);

        ListNode reverseHead=reverse(mid.next);

        mid.next=reverseHead;

        //comparing ll

        ListNode temp1=head;
        ListNode temp2=reverseHead;
        while(temp2!=null){
            if(temp1.val!=temp2.val)
                return false;
            temp1=temp1.next;
            temp2=temp2.next;
        }
    return true;
        
    }
}

```
