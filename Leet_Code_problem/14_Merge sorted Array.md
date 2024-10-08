# Merge sorted Array
You are given two integer arrays nums1 and nums2, sorted in non-decreasing order, and two integers m and n, representing the number of elements in nums1 and nums2 respectively.

Merge nums1 and nums2 into a single array sorted in non-decreasing order.

The final sorted array should not be returned by the function, but instead be stored inside the array nums1. To accommodate this, nums1 has a length of m + n, where the first m elements denote the elements that should be merged, and the last n elements are set to 0 and should be ignored. nums2 has a length of n.

 

Example 1:

Input: nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3
Output: [1,2,2,3,5,6]
Explanation: The arrays we are merging are [1,2,3] and [2,5,6].
The result of the merge is [1,2,2,3,5,6] with the underlined elements coming from nums1.
 

Constraints:

    nums1.length == m + n
    nums2.length == n
    0 <= m, n <= 200
    1 <= m + n <= 200
    -109 <= nums1[i], nums2[j] <= 109

# Java
```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) { 
        int i,j=0;
        for(i=m,j=0;j<n;j++){
            nums1[i]=nums2[j];
            i++;
            
        }
            Arrays.sort(nums1);
    }
        
}
```
Another Approach

```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) { 
        int result[] =new int [m+n];
        int i=0,j=0;
        int p=0;
        while(i<m || j<n){
            int val1=(i<m)?nums1[i]:Integer.MAX_VALUE;
            int val2=(j<n)?nums2[j]:Integer.MAX_VALUE;
            if(val1<val2){
                result[p]=val1;
                i++;
            }else{
                result[p]=val2;
                j++;
            }
            p++;
        }

        for(int k=0;k<m+n;k++){
            nums1[k]=result[k];
        }
    
        
    }
        
}
```
