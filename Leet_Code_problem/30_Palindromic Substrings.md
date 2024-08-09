# 647. Palindromic Substrings

Given a string s, return the number of palindromic substrings in it.

A string is a palindrome when it reads the same backward as forward.

A substring is a contiguous sequence of characters within the string.

 

Example 1:

Input: s = "abc"
Output: 3
Explanation: Three palindromic strings: "a", "b", "c".

Example 2:

Input: s = "aaa"
Output: 6
Explanation: Six palindromic strings: "a", "a", "a", "aa", "aa", "aaa".

 

Constraints:

    1 <= s.length <= 1000
    s consists of lowercase English letters.

# Java
```
class Solution {

    int expandCount(String s,int i, int j){
        int count=0;
        while(i>=0 && j<s.length() && s.charAt(i)==s.charAt(j)){
            count++;
            i--;
            j++;
        }
        return count;
    }
    public int countSubstrings(String s) {
        int totalCount=0;
        int n=s.length();
        for(int i=0;i<n;i++){
            int oddans=expandCount(s,i,i);
                totalCount=totalCount+oddans;
            int evenans=expandCount(s,i,i+1);
                totalCount=totalCount+evenans;
        }
        return totalCount;
        
    }
}
```
