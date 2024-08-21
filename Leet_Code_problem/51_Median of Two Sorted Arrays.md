# 4. Median of Two Sorted Arrays

Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.

The overall run time complexity should be O(log (m+n)).

 
Example 1:

Input: nums1 = [1,3], nums2 = [2]
Output: 2.00000
Explanation: merged array = [1,2,3] and median is 2.

Example 2:

Input: nums1 = [1,2], nums2 = [3,4]
Output: 2.50000
Explanation: merged array = [1,2,3,4] and median is (2 + 3) / 2 = 2.5.


Constraints:

    nums1.length == m
    nums2.length == n
    0 <= m <= 1000
    0 <= n <= 1000
    1 <= m + n <= 2000
    -106 <= nums1[i], nums2[i] <= 106

# Java
```
class Solution {
    public int [] merge(int arr1[], int arr2[]){
        int p1=0,p2=0,p3=0;
        int ans[]=new int[arr1.length+arr2.length];

        while(p1<arr1.length || p2<arr2.length){

            int val1=p1<arr1.length?arr1[p1]:Integer.MAX_VALUE;
            int val2=p2<arr2.length?arr2[p2]:Integer.MAX_VALUE;

            if(val1<val2){
                ans[p3]=val1;
                p1++;
            }
            else{
                ans[p3]=val2;
                p2++;
            }
            p3++;
        }
        return ans;
    }
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        int ans[]=merge(nums1,nums2);
        double result=0;
        if(ans.length%2==0){
                result=(double)(ans[ans.length/2]+ ans[ans.length/2-1])/2;
        }
        else
            result=(double)(ans[ans.length/2]);
        
        return result;
    }
    
}

```
