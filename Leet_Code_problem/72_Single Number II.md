# 137. Single Number II

Given an integer array nums where every element appears three times except for one, which appears exactly once. Find the single element and return it.

You must implement a solution with a linear runtime complexity and use only constant extra space.

 

Example 1:

Input: nums = [2,2,3,2]
Output: 3

Example 2:

Input: nums = [0,1,0,1,0,1,99]
Output: 99

 

Constraints:

    1 <= nums.length <= 3 * 104
    -231 <= nums[i] <= 231 - 1
    Each element in nums appears exactly three times except for one element which appears once.

# Java
```java
class Solution {
    public int singleNumber(int[] nums) {
        HashMap<Integer,Integer> ans=new HashMap<>();

        for(int i=0;i<nums.length;i++){
            if(!ans.containsKey(nums[i])){
                ans.put(nums[i],1);
            }
            else{
                int ele=ans.get(nums[i]);
                ans.put(nums[i],ans.get(nums[i])+1);
            }
        }

        for(int i=0;i<nums.length;i++){
            if(ans.get(nums[i])==1)
                return nums[i];
        }

        return -1;
    }
}
```
