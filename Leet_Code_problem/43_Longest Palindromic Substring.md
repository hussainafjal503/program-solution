# 5. Longest Palindromic Substring

Given a string s, return the longest
palindromic
substring
in s.

 
Example 1:

Input: s = "babad"
Output: "bab"
Explanation: "aba" is also a valid answer.

Example 2:

Input: s = "cbbd"
Output: "bb"


Constraints:

    1 <= s.length <= 1000
    s consist of only digits and English letters.

# Java
```
class Solution {
    public String longestPalindrome(String s) {
        if(s.length()<=1)
            return s;

        String longestPs="";
        for(int i=1;i<s.length();i++){

            //for odd indexing
            int low=i,high=i;
            while(s.charAt(low)==s.charAt(high)){
                low--;
                high++;

                //condition for outof bound indexing
                if(low==-1 || high==s.length())
                    break;
            }

            String palind=s.substring(low+1,high);
            //checking the length of the palindrom 
            if(palind.length()>longestPs.length()){
                longestPs=palind;
            }


            //for even no indexing
            low=i-1;
            high=i;
            while(s.charAt(low)==s.charAt(high)){
                low--;
                high++;
                
                //condition for outof bound indexing
                if(low==-1 || high==s.length())
                    break;
            }

            palind=s.substring(low+1,high);
            if(palind.length()>longestPs.length()){
                longestPs=palind;
            }

        }
        return longestPs;
        
    }
}
```
