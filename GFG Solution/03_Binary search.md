# Binary search

Given a sorted array of size N and an integer K, find the position(0-based indexing) at which K is present in the array using binary search.

Example 1:

Input: N = 5 arr[] = {1 2 3 4 5} K = 4 Output: 3 Explanation: 4 appears at index 3.
# c++
```
class Solution {
    int binarysearch(int arr[], int n, int k) {
        // code 
        int start=0,end=n-1,mid;
        while(start<=end)
        {
            //mid=start+(end-start)/2;
            mid=(start+end)/2;
            if(arr[mid]==k)
                return mid;
            else if(arr[mid]<k)
                start=mid+1;
            else
                end=mid-1;
        }
        return -1;
    }
}
```
