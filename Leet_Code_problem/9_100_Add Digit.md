# 258. Add Digits

Given an integer num, repeatedly add all its digits until the result has only one digit, and return it.

 

Example 1:

Input: num = 38
Output: 2
Explanation: The process is
38 --> 3 + 8 --> 11
11 --> 1 + 1 --> 2 
Since 2 has only one digit, return it.

Example 2:

Input: num = 0
Output: 0

 

Constraints:

    0 <= num <= 231 - 1

 

Follow up: Could you do it without any loop/recursion in O(1) runtime?
# Java
```java
class Solution {
    public int addDigits(int num) {
        if(num<10)
            return num;
       String str=num+"";
       int sum=0;
       for(int i=0;i<str.length();i++){
             sum+=Character.getNumericValue(str.charAt(i));
       }
    
       int n=addDigits(sum);

       return n;
       
        
    }
}

```
