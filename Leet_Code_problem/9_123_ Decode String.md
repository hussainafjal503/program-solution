# 394. Decode String


Given an encoded string, return its decoded string.

The encoding rule is: k[encoded_string], where the encoded_string inside the square brackets is being repeated exactly k times. Note that k is guaranteed to be a positive integer.

You may assume that the input string is always valid; there are no extra white spaces, square brackets are well-formed, etc. Furthermore, you may assume that the original data does not contain any digits and that digits are only for those repeat numbers, k. For example, there will not be input like 3a or 2[4].

The test cases are generated so that the length of the output will never exceed 105.

 

Example 1:

Input: s = "3[a]2[bc]"
Output: "aaabcbc"

Example 2:

Input: s = "3[a2[c]]"
Output: "accaccacc"

Example 3:

Input: s = "2[abc]3[cd]ef"
Output: "abcabccdcdcdef"

 

Constraints:

    1 <= s.length <= 30
    s consists of lowercase English letters, digits, and square brackets '[]'.
    s is guaranteed to be a valid input.
    All the integers in s are in the range [1, 300].

# Java
```java
class Solution {
    public String decodeString(String s) {
        Stack<Integer> numberSt=new Stack<>();
        Stack<String> mainSt=new Stack<>();
        for(int i=0;i<s.length();i++){
            char ch=s.charAt(i);
            if(ch>='0' && ch<='9'){
                int num=0;

                while(i<s.length() && s.charAt(i)>='0' && s.charAt(i)<='9'){
                    num=num*10+(int)(s.charAt(i)-'0');
                    i++;
                }

                i--;
                numberSt.push(num);

            }
            else if(ch!=']'){
                mainSt.push(ch+"");
            }

            else{
                String str="";
                while(!mainSt.peek().equals("[")){
                    str=mainSt.pop()+str;
                }

                mainSt.pop();
                int repeatNum=numberSt.pop();
                StringBuilder sb=new StringBuilder("");

                while(repeatNum>0){
                    sb.append(str);
                    repeatNum--;
                }

                mainSt.push(sb.toString());
            }
        }
        
        StringBuilder ans=new StringBuilder("");
        while(mainSt.size()>0){
            ans.insert(0,mainSt.pop());
        }
        return ans.toString();
    }
}
```
