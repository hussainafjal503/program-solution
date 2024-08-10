# 917. Reverse Only Letters

Given a string s, reverse the string according to the following rules:

    All the characters that are not English letters remain in the same position.
    All the English letters (lowercase or uppercase) should be reversed.

Return s after reversing it.

 

Example 1:

Input: s = "ab-cd"
Output: "dc-ba"

Example 2:

Input: s = "a-bC-dEf-ghIj"
Output: "j-Ih-gfE-dCba"

Example 3:

Input: s = "Test1ng-Leet=code-Q!"
Output: "Qedo1ct-eeLg=ntse-T!"

 

Constraints:

    1 <= s.length <= 100
    s consists of characters with ASCII values in the range [33, 122].
    s does not contain '\"' or '\\'.

# Java
```
class Solution {
    public String reverseOnlyLetters(String s) {
       char ans []=s.toCharArray();
        int l=0;
        int h=ans.length-1;
        while(l<h){
            if(Character.isAlphabetic(ans[l]) && Character.isAlphabetic(ans[h])){
                char temp=ans[l];
                ans[l]=ans[h];
                ans[h]=temp;
                l++;
                h--;
            }
            else if(! Character.isAlphabetic(ans[l]))
                l++;
            else
                h--;
                
        }
         String result =new String(ans);
        return result;
    }
}
```
