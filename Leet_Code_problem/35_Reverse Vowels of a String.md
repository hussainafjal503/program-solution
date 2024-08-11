# 345. Reverse Vowels of a String

Given a string s, reverse only all the vowels in the string and return it.

The vowels are 'a', 'e', 'i', 'o', and 'u', and they can appear in both lower and upper cases, more than once.

 

Example 1:

Input: s = "hello"
Output: "holle"

Example 2:

Input: s = "leetcode"
Output: "leotcede"

 

Constraints:

    1 <= s.length <= 3 * 105
    s consist of printable ASCII characters.

# Java
```

class Solution {

    public boolean isVowel(char ch){
        ch=Character.toLowerCase(ch);

        if( ch=='a' || ch=='e' || ch=='i' || ch=='o' || ch=='u')
            return true;
        else 
            return false;
    }

    private void swap(char [] word, int s,int e){
        char temp=word[s];
        word[s]=word[e];
        word[e]=temp;
    }
    public String reverseVowels(String s) {
        char [] str=s.toCharArray();
        int l=0;
        int h=s.length()-1;

        while(l<h){
            if(isVowel(str[l]) && isVowel(str[h])){
               swap(str,l,h);
                l++;
                h--;
            }
            else if(isVowel(str[l])==false)
                l++;
            else
                h--;
        }
       String result=new String(str);
       return result;
        
    }
}
```
