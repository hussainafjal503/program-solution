# 242. Valid Anagram

Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

 

Example 1:

Input: s = "anagram", t = "nagaram"
Output: true

Example 2:

Input: s = "rat", t = "car"
Output: false

 

Constraints:

    1 <= s.length, t.length <= 5 * 104
    s and t consist of lowercase English letters.

# Java
```
class Solution {
    public boolean isAnagram(String s, String t) {
      
    int table[]=new int[256];
    for( int i = 0; i < s.length(); i++){
        table[s.codePointAt(i)]++;
    }
        
    for( int i = 0; i < t.length(); i++){
        table[t.codePointAt(i)]--;
    }
    
    for(int i=0;i<256;i++){
        if(table[i]!=0)
            return false;
    }
    return true;
    }
}
```
