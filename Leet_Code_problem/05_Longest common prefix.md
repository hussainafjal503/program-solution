# Longest common prefix
Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

 

Example 1:

Input: strs = ["flower","flow","flight"]
Output: "fl"

Example 2:

Input: strs = ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.

 

Constraints:

    1 <= strs.length <= 200
    0 <= strs[i].length <= 200
    strs[i] consists of only lowercase English letters.

```
c++
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        
       
        if(strs.size()==0)
            return "";
        
        string prefix="";
        for(int i=0;i<strs[0].length();i++){
            char ch=strs[0][i];
            for(string s:strs){
                if(ch==s[i]){
                    continue;
                }
                else{
                    return prefix;
                }
            }
           prefix+=ch;
        }

       return prefix; 
    }
};
```
