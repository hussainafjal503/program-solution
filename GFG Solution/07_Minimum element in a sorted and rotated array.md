# Minimum element in a sorted and rotated array

A sorted(in ascending order) array A[ ] with distinct elements is rotated at some unknown point, the task is to find the minimum element in it.

Example 1

Input: N = 5 arr[] = {4 ,5 ,1 ,2 ,3} Output: 1 Explanation: 1 is the minimum element in the array.
# c++
```
class Solution{
public:
    int findMin(int arr[], int n){
        //complete the function here
        int start=0, end=n-1, mid, ans=arr[0];
        
        while(start<=end)
        {
            mid=start+(end-start)/2;
            //left side
            if(arr[mid]>=arr[0])
                start=mid+1;
                //right side
            else
            {
                ans=arr[mid];
                end=mid-1;
            }
        }
        return ans;
    }
};
```
