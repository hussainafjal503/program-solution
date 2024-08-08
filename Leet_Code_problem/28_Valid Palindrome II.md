# 680. Valid Palindrome II

Given a string s, return true if the s can be palindrome after deleting at most one character from it.

 

Example 1:

Input: s = "aba"
Output: true

Example 2:

Input: s = "abca"
Output: true
Explanation: You could delete the character 'c'.

Example 3:

Input: s = "abc"
Output: false

 

Constraints:

    1 <= s.length <= 105
    s consists of lowercase English letters.

# Java
```
class Solution {
    public boolean validPalindrome(String str) {
        int s=0;
        int e=str.length()-1;
        while(s<=e){
            if(str.charAt(s)!=str.charAt(e))
                return checkPalindrom(str,s+1,e)|| (checkPalindrom(str,s,e-1));
            else{
                s++;
                e--;
            }
        }
        return true;
    }
    public boolean checkPalindrom(String str, int s, int e){
        while(s<=e){
            if(str.charAt(s)!=str.charAt(e))
                return false;
            else{
                s++;
                e--;
            }
        }
        return true;
    }
}
```
