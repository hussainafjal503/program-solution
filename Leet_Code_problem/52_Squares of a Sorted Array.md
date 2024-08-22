# 977. Squares of a Sorted Array

Given an integer array nums sorted in non-decreasing order, return an array of the squares of each number sorted in non-decreasing order.

 
Example 1:

Input: nums = [-4,-1,0,3,10]
Output: [0,1,9,16,100]
Explanation: After squaring, the array becomes [16,1,0,9,100].
After sorting, it becomes [0,1,9,16,100].

Example 2:

Input: nums = [-7,-3,2,3,11]
Output: [4,9,9,49,121]
 

Constraints:

    1 <= nums.length <= 104
    -104 <= nums[i] <= 104
    nums is sorted in non-decreasing order.

 
Follow up: Squaring each element and sorting the new array is very trivial, could you find an O(n) solution using a different approach?

# Java
```
class Solution {
    public int[] sortedSquares(int[] nums) {
        int []result=new int[nums.length];
        int s=0,e=nums.length-1,p=result.length-1;

        while(s<=e){
            int val1=Math.abs((int)Math.pow(nums[s],2));
            int val2=Math.abs((int)Math.pow(nums[e],2));
            if(val1>val2){
                result[p]=val1;
                s++;
            }
            else{
                result[p]=val2;
                e--;
            }
            p--;
        }
        return result;
    }
}
```
