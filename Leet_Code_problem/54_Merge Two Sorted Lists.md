# 21. Merge Two Sorted Lists

You are given the heads of two sorted linked lists list1 and list2.

Merge the two lists into one sorted list. The list should be made by splicing together the nodes of the first two lists.

Return the head of the merged linked list.


Example 1:

Input: list1 = [1,2,4], list2 = [1,3,4]
Output: [1,1,2,3,4,4]

Example 2:

Input: list1 = [], list2 = []
Output: []

Example 3:

Input: list1 = [], list2 = [0]
Output: [0]

 

Constraints:

    The number of nodes in both lists is in the range [0, 50].
    -100 <= Node.val <= 100
    Both list1 and list2 are sorted in non-decreasing order.

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
    public ListNode mergeTwoLists(ListNode l1, ListNode l2) {
        // if(l1 == null) return l2;
		// if(l2 == null) return l1;
		// if(l1.val < l2.val){
		// 	l1.next = mergeTwoLists(l1.next, l2);
		// 	return l1;
		// } else{
		// 	l2.next = mergeTwoLists(l1, l2.next);
		// 	return l2 ;
		// }
        ListNode ans=new ListNode(Integer.MIN_VALUE);

        ListNode head=ans;
        if(l1==null)
            return l2;
        else if(l2==null)
            return l1;

        while(l1!=null && l2!=null){
            if(l1.val<=l2.val){
                ans.next=l1;
                l1=l1.next;
            }
            else{
                ans.next=l2;
                l2=l2.next;
            }
            ans=ans.next;
        }
        
        if(l1!=null)
             ans.next=l1;
        else if(l2!=null)
            ans.next=l2;

        return head.next;
        
    }
}
```
