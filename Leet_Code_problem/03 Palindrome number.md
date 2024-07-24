# Palindrome number
Given an integer x, return true if x is a
palindrome
, and false otherwise.

 

Example 1:

Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.

Example 2:

Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
```
c++
class Solution {
public:
    bool isPalindrome(int x) {
        long long temp=x;
        long long result=0;
        if(x<0)
            return false;
        while(x>0)
        {
           
            result=result*10+x%10;
            x/=10;
        }
        if(result==temp)
            return true;
        else
            return false;
        
    }
};
```
