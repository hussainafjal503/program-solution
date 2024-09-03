# 912. Sort an Array

Given an array of integers nums, sort the array in ascending order and return it.

You must solve the problem without using any built-in functions in O(nlog(n)) time complexity and with the smallest space complexity possible.


Example 1:

Input: nums = [5,2,3,1]
Output: [1,2,3,5]
Explanation: After sorting the array, the positions of some numbers are not changed (for example, 2 and 3), while the positions of other numbers are changed (for example, 1 and 5).

Example 2:

Input: nums = [5,1,1,2,0,0]
Output: [0,0,1,1,2,5]
Explanation: Note that the values of nums are not necessairly unique.

 
Constraints:

    1 <= nums.length <= 5 * 104
    -5 * 104 <= nums[i] <= 5 * 104

# Java
```java
class Solution {
    public int[] sortArray(int[] nums) {
        mergeSort(nums,0,nums.length-1);
        return nums;
        
    }

    public void mergeSort(int[]nums, int start, int end){
        if(start>=end)
            return;
        int mid=start+(end-start)/2;
        
        mergeSort(nums,start,mid);
        mergeSort(nums,mid+1,end);

        merge(nums,start,mid,end);
    }

    public void merge(int[]nums,int start, int mid, int end){
        int totalsize=end-start+1;
        int gap=((totalsize/2) + (totalsize%2));

        while(gap>0){

            int i=start;
            int j=start+gap;
            while(j<=end){
                if(nums[i]>nums[j]){
                    int temp=nums[i];
                    nums[i]=nums[j];
                    nums[j]=temp;
                }
                i++;
                j++;
            }
            gap=gap<=1?0: (gap/2)+(gap%2);
        }
    }
}
```
