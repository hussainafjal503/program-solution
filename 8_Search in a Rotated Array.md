# Search in a Rotated Array

Given a sorted and rotated array A of n distinct elements which is rotated at some point, and given an element key. The task is to find the index of the given element key in the array A. The whole array A is given as the range to search.
Note:- You are given l and h where l=0 and h=n-1.

Example 1:

Input:
n = 9
A[] = {5, 6, 7, 8, 9, 10, 1, 2, 3}
key = 10
l = 0 , h = 8
Output:
5
Explanation: 
10 is found at index 5.
```c++
class Solution {
  public:
    int search(int A[], int start, int end, int key) {
        // l: The starting index
        // h: The ending index, you have to search the key in this range

        // complete the function here
        
        int mid,ans=-1;
        while(start<=end)
        {
            mid=start+(end-start)/2;
            
            if(A[mid]==key)
                return mid;
                //left side
            else if(A[mid]>=A[0])
            {
                if(A[start]<=key && A[mid]>=key)
                    end=mid-1;
                else
                    start=mid+1;
            }
            //right
            else
            {
                if(A[mid]<=key && A[end]>=key)
                    start=mid+1;
                else
                    end=mid-1;
                
            }
        }
        return ans;
    }
};
```
