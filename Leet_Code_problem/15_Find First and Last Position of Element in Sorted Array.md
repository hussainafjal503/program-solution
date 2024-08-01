# Find First and Last Position of Element in Sorted Array

Given an array of integers nums sorted in non-decreasing order, find the starting and ending position of a given target value.

If target is not found in the array, return [-1, -1].

You must write an algorithm with O(log n) runtime complexity.

 

Example 1:

Input: nums = [5,7,7,8,8,10], target = 8
Output: [3,4]

Example 2:

Input: nums = [5,7,7,8,8,10], target = 6
Output: [-1,-1]


Constraints:

    0 <= nums.length <= 105
    -109 <= nums[i] <= 109
    nums is a non-decreasing array.
    -109 <= target <= 109

# java

```
class Solution {
    public int[] searchRange(int[] nums, int target) {
        int result[]=new int[2];
        int s=0;
        int e=nums.length-1;
        int mid;
        int first=-1;
        int second=-1;
        while(s<=e){
            mid=s+(e-s)/2;
            if(nums[mid]==target){
                first=mid;
                e=mid-1;
            }
            else if(nums[mid]<target){
                //right search
                s=mid+1;
            }
            else
                e=mid-1;
        }
        
        s=0;
        e=nums.length-1;
        while(s<=e){
            mid=s+(e-s)/2;
            if(nums[mid]==target){
                second=mid;
                s=mid+1;
            }
            else if(nums[mid]<target){
                //right search
                s=mid+1;
            }
            else
                e=mid-1;
        }

        result[0]=first;
        result[1]=second;

        return result;
    }
}
```
