# 2. Add Two Numbers

You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

Example 1:

Input: l1 = [2,4,3], l2 = [5,6,4]
Output: [7,0,8]
Explanation: 342 + 465 = 807.

Example 2:

Input: l1 = [0], l2 = [0]
Output: [0]

Example 3:

Input: l1 = [9,9,9,9,9,9,9], l2 = [9,9,9,9]
Output: [8,9,9,9,0,0,0,1]

 
Constraints:

    The number of nodes in each linked list is in the range [1, 100].
    0 <= Node.val <= 9
    It is guaranteed that the list represents a number that does not have leading zeros.

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
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode it1=l1;
        ListNode it2=l2;

        ListNode temp=new ListNode(-1);
        ListNode it3=temp;
        int carry=0;

        while(it1!=null && it2!=null){
            int n=it1.val+it2.val+carry;
            int digit=n%10;
            carry=n/10;
            
            ListNode newnode=new ListNode(digit);
            it3.next=newnode;
            it3=newnode;
            it1=it1.next;
            it2=it2.next;
        }

        while(it1!=null){
            int n=carry+it1.val;
            int digit=n%10;
            carry=n/10;
            ListNode newNode=new ListNode(digit);
            it3.next=newNode;
            it3=newNode;
            it1=it1.next;
        }
        while(it2!=null){

            int n=carry+it2.val;
            int digit=n%10;
            carry=n/10;
            ListNode newNode=new ListNode(digit);
            it3.next=newNode;
            it3=newNode;
            it2=it2.next;
        }
        
        if(carry>0){
            ListNode newNode=new ListNode(carry);
            it3.next=newNode;
        }

        return temp=temp.next;        
    }
}
```
