# Search in Rotated Sorted Array


There is an integer array nums sorted in ascending order (with distinct values).

Prior to being passed to your function, nums is possibly rotated at an unknown pivot index k (1 <= k < nums.length) such that the resulting array is [nums[k], nums[k+1], ..., nums[n-1], nums[0], nums[1], ..., nums[k-1]] (0-indexed). For example, [0,1,2,4,5,6,7] might be rotated at pivot index 3 and become [4,5,6,7,0,1,2].

Given the array nums after the possible rotation and an integer target, return the index of target if it is in nums, or -1 if it is not in nums.

You must write an algorithm with O(log n) runtime complexity.

 
Example 1:

Input: nums = [4,5,6,7,0,1,2], target = 0
Output: 4

Example 2:

Input: nums = [4,5,6,7,0,1,2], target = 3
Output: -1

Example 3:

Input: nums = [1], target = 0
Output: -1


Constraints:

    1 <= nums.length <= 5000
    -104 <= nums[i] <= 104
    All values of nums are unique.
    nums is an ascending array that is possibly rotated.
    -104 <= target <= 104

# java
```
class Solution {
    public int findPivot(int [] nums){
         int s=0;
        int e=nums.length-1;
        int mid;
        while(s<=e){
            mid=s+(e-s)/2;
            if(s==e)
                return s;
            else if(mid+1<=e && nums[mid]>nums[mid+1])
                return mid;
            else if(mid-1>=s && nums[mid-1]>nums[mid])
                return  mid-1;
            else if(nums[s]>nums[mid])
                e=mid-1;
            else
                s=mid+1;
        }
        return -1;

    }
    public int binarySearch(int [] nums, int s,int e,int target){
        while(s<=e){
            int mid=s+(e-s)/2;
            if(nums[mid]==target)
                return mid;
            else if(target>nums[mid])
                s=mid+1;
            else 
                e=mid-1;
        }
        return-1;
    }
    public int search(int[] nums, int target) {
    
        int pivot=findPivot(nums);
        int ans=0;
        if(target>=nums[0] && target<=nums[pivot])
            ans=binarySearch(nums,0,pivot,target);
       
        else
            ans=binarySearch(nums,pivot+1,nums.length-1,target);

        return ans;
    }
  
}
```

