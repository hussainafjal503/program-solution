# First and last occurrences of X

Given a sorted array having N elements, find the indices of the first and last occurrences of an element X in the given array.

Note: If the number X is not found in the array, return '-1' as an array.

Example 1:

Input: N = 4 , X = 3 arr[] = { 1, 3, 3, 4 } Output: 1 2 Explanation: For the above array, first occurence of X = 3 is at index = 1 and last occurence is at index = 2.
# c++
```
class Solution{
public:
 vector<int> firstAndLast(vector<int> &arr, int n, int x) {
        // Code here
        
         int start=0;
        int end=n-1;
        int mid;
        int first=-1,last=-1;
        
        
        //find first
        while(start<=end)
        {
            mid=start+(end-start)/2;
            if(arr[mid]==x)
            {
                first=mid;
                end=mid-1;
                
            }
            else if(arr[mid]<x)
            {
                start=mid+1;
            }
            else
                end=mid-1;
        }
        
        //finding last element
        start=0;
        end=n-1;
        while(start<=end)
        {
            mid=start+(end-start)/2;
            if(arr[mid]==x)
            {
                last=mid;
                start=mid+1;
            }
            else if(arr[mid]<x)
                start=mid+1;
            else
                end=mid-1;
        }
        
        vector<int>a(2);
        vector<int>b(1);
       
            a[0]=first;
            a[1]=last;
            b[0]=-1;
        if(a[0]>-1 && a[1]>-1)
        {
            return a;
        }
        else
            return b;
        
        
    }
};
```
