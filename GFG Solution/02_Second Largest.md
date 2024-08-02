# Second Largest

Given an array Arr of size N, print the second largest distinct element from an array. If the second largest element doesn't exist then return -1.

Example 1:

Input: N = 6 Arr[] = {12, 35, 1, 10, 34, 1} Output: 34 Explanation: The largest element of the array is 35 and the second largest element is 34.

# c++
```
class Solution{
public:	
	// Function returns the second
	// largest elements
	int print2largest(int arr[], int n) {
	    
	    // code here
	    int ans=-1;
	    //finding largest
	    for(int i=0;i<n;i++)
	    {
	        if(arr[i]>ans)
	            ans=arr[i];
	    }
	    //finding second largest
	    int second=-1;
	    
	    for(int i=0;i<n;i++)
	    {
	        if(arr[i]!=ans)
	        second=max(second,arr[i]);
	    }
	    return second;
	}
};
```
