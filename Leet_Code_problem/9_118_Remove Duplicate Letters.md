# 316. Remove Duplicate Letters

Given a string s, remove duplicate letters so that every letter appears once and only once. You must make sure your result is
the smallest in lexicographical order
among all possible results.

 

Example 1:

Input: s = "bcabc"
Output: "abc"

Example 2:

Input: s = "cbacdcbc"
Output: "acdb"

 

Constraints:

    1 <= s.length <= 104
    s consists of lowercase English letters.

 # Java
 ```java
class Solution {
    public String removeDuplicateLetters(String s) {
        int []lastInd=new int[26];
        for( int i=0;i<s.length();i++){
            char ch=s.charAt(i);
            int idx=(int)(ch-'a');

            lastInd[idx]=i;
        }
    
        boolean [] present=new boolean[26];
        Stack<Character> st=new Stack<>();

        for(int i=0;i<s.length();i++){
            char ch=s.charAt(i);
            int idx=(int) (ch-'a');
            if(present[idx]==false){
                while(st.size()>0 && st.peek()>ch && lastInd[(int)(st.peek()-'a')]>i){
                    present[(int)(st.peek()-'a')]=false;
                    st.pop();
                }
                st.push(ch);
                present[idx]=true;
            }
           
        }

        StringBuilder str= new StringBuilder("");
        while(st.size()!=0){
            str.append(st.pop());
        }
        return str.reverse().toString();
        
    }
}
```
