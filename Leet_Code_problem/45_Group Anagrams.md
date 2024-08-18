# 49. Group Anagrams

Given an array of strings strs, group the anagrams together. You can return the answer in any order.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.


Example 1:

Input: strs = ["eat","tea","tan","ate","nat","bat"]
Output: [["bat"],["nat","tan"],["ate","eat","tea"]]

Example 2:

Input: strs = [""]
Output: [[""]]

Example 3:

Input: strs = ["a"]
Output: [["a"]]
 

Constraints:

    1 <= strs.length <= 104
    0 <= strs[i].length <= 100
    strs[i] consists of lowercase English letters.

# Java
```
class Solution {
    public List<List<String>> groupAnagrams(String[] strs) {
        if(strs==null || strs.length==0)
            return new ArrayList<>();

        Map<String,List<String>> frequencyMap= new HashMap<>();

        for(String str:strs){

            String frequency=getFrequency(str);

            if(frequencyMap.containsKey(frequency)){
                frequencyMap.get(frequency).add(str);
            }

            else{
                List<String>strList=new ArrayList<>();
                strList.add(str);
                
                frequencyMap.put(frequency, strList);
            }
        }
        return new ArrayList(frequencyMap.values());
        
    }

    private String getFrequency(String str){
        int []freq=new int[26];

        for(char c:str.toCharArray()){
            freq[c-'a']++;
        }

        //creating the frequency string
        StringBuilder frequencyString=new StringBuilder("");

        char c='a';
        for(int i:freq){
            frequencyString.append(c);
            frequencyString.append(i);
            c++;
        }
        return frequencyString.toString();
    }
}
```
