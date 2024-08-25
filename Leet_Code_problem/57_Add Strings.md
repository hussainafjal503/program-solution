# 415. Add Strings

Given two non-negative integers, num1 and num2 represented as string, return the sum of num1 and num2 as a string.

You must solve the problem without using any built-in library for handling large integers (such as BigInteger). You must also not convert the inputs to integers directly.

 
Example 1:

Input: num1 = "11", num2 = "123"
Output: "134"

Example 2:

Input: num1 = "456", num2 = "77"
Output: "533"

Example 3:

Input: num1 = "0", num2 = "0"
Output: "0" 

Constraints:

    1 <= num1.length, num2.length <= 104
    num1 and num2 consist of only digits.
    num1 and num2 don't have any leading zeros except for the zero itself.
# Java
```java
class Solution {
    public String addStrings(String num1, String num2) {
        int p1=num1.length()-1,p2=num2.length()-1;
        StringBuilder ans=new StringBuilder();
        int sum,carry=0;
        while(p1>=0 || p2>=0){
            int digit1=(p1>=0)?num1.charAt(p1)-'0':0;
            int digit2=(p2>=0)?num2.charAt(p2)-'0':0;
            sum=digit1+digit2+carry;
            ans.append(sum%10);
            carry=sum/10;
            p1--;
            p2--;
            
        }
        if(carry!=0)
            ans.append(carry);

      return ans.reverse().toString();
        
    }
}
```