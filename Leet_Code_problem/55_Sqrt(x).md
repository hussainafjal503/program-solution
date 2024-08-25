# 69. Sqrt(x)

Given a non-negative integer x, return the square root of x rounded down to the nearest integer. The returned integer should be non-negative as well.

You must not use any built-in exponent function or operator.

    For example, do not use pow(x, 0.5) in c++ or x ** 0.5 in python.


Example 1:

Input: x = 4
Output: 2
Explanation: The square root of 4 is 2, so we return 2.

Example 2:

Input: x = 8
Output: 2
Explanation: The square root of 8 is 2.82842..., and since we round it down to the nearest integer, 2 is returned.

 

Constraints:

    0 <= x <= 231 - 1
# Java
```java
class Solution {
    public int mySqrt(int x) {
    int s=0,e=x;
    int ans=0;
    while(s<=e){
        int mid=s+(e-s)/2;
        if(x==0)
            return 0;
        else if(x==1)
            return 1;
        if(mid*mid==x)
            return mid;
        else if((long)mid*mid<x){
            ans=mid;
            s=mid+1;
        }
        else
            e=mid-1;
    }
    return ans;
    }
}
```
