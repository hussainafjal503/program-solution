# 442. Find All Duplicates in an Array

Given an integer array nums of length n where all the integers of nums are in the range [1, n] and each integer appears once or twice, return an array of all the integers that appears twice.

You must write an algorithm that runs in O(n) time and uses only constant extra space.

 

Example 1:

Input: nums = [4,3,2,7,8,2,3,1]
Output: [2,3]

Example 2:

Input: nums = [1,1,2]
Output: [1]

Example 3:

Input: nums = [1]
Output: []

Constraints:

    n == nums.length
    1 <= n <= 105
    1 <= nums[i] <= n
    Each element in nums appears once or twice.

# Java
```
class Solution {
    public List<Integer> findDuplicates(int[] nums) {
        List <Integer> result=new ArrayList<>();

        for(int i=0;i<nums.length;i++){

            int index=Math.abs(nums[i])-1;  //finding index of the element

            if(nums[index]<0)
                result.add(index+1);    //adding element in result list
            
            nums[index]=nums[index]*-1; //marking all value to negative
        }
        
        return result;
    }
}

```
