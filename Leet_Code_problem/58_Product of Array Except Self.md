# 238. Product of Array Except Self

Given an integer array nums, return an array answer such that answer[i] is equal to the product of all the elements of nums except nums[i].

The product of any prefix or suffix of nums is guaranteed to fit in a 32-bit integer.

You must write an algorithm that runs in O(n) time and without using the division operation.

 
Example 1:

Input: nums = [1,2,3,4]
Output: [24,12,8,6]

Example 2:

Input: nums = [-1,1,0,-3,3]
Output: [0,0,9,0,0]


Constraints:

    2 <= nums.length <= 105
    -30 <= nums[i] <= 30
    The product of any prefix or suffix of nums is guaranteed to fit in a 32-bit integer.

 
Follow up: Can you solve the problem in O(1) extra space complexity? (The output array does not count as extra space for space complexity analysis.)

# Java
```java
class Solution {
    public int[] productExceptSelf(int[] nums) {
        int n=nums.length;
        int right[]=new int[n];
        int product=1;
        for(int i=n-1;i>=0;i--){
            product*=nums[i];
            right[i]=product;
        }
        int result[]=new int[n];
        int left=1;
        for(int i=0;i<n-1;i++){
            int val=left*right[i+1];
            result[i]=val;
            left*=nums[i];
        }
        result[n-1]=left;
        return result;
        
    }
}
```
Another approach
```java
class Solution {
    public int[] productExceptSelf(int[] nums) {
       

        int n=nums.length;
        int ans[]=new int[n];
        ans[0]=1;
        for(int i=1;i<n;i++){
            ans[i]=ans[i-1]*nums[i-1];
        }

        int suffix[]=new int[n];
        suffix[n-1]=1;
        for(int i=n-2;i>=0;i--){
            suffix[i]=suffix[i+1]*nums[i+1];
        }
        int result[]=new int[n];
        for(int i=0;i<n;i++){
            result[i]=ans[i]*suffix[i];
        }
        return result;
        
    }
}
```
