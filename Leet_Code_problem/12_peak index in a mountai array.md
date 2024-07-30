# peak index in a mountai array

You are given an integer mountain array arr of length n where the values increase to a peak element and then decrease.

Return the index of the peak element.

Your task is to solve it in O(log(n)) time complexity.

 

Example 1:

Input: arr = [0,1,0]

Output: 1

Example 2:

Input: arr = [0,2,1,0]

Output: 1

Example 3:

Input: arr = [0,10,5,2]

Output: 1

 

Constraints:

    3 <= arr.length <= 105
    0 <= arr[i] <= 106
    arr is guaranteed to be a mountain array.

# java
```
class Solution {
    public int peakIndexInMountainArray(int[] arr) {
        
        int s=0;
        int e=arr.length-1;
        int mid;
        while(s<e){
            mid=s+(e-s)/2;
            if(arr[mid]<arr[mid+1])
                s=mid+1;
            else
                e=mid;
        }
        return s;
    }
}
```
