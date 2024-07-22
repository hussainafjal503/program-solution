# reverse integer
Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-231, 231 - 1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).

 

Example 1:

Input: x = 123
Output: 321

Example 2:

Input: x = -123
Output: -321

Example 3:

Input: x = 120
Output: 21

 

Constraints:

    -231 <= x <= 231 - 1

```
c++
class Solution {
public:
    int reverse(int x) {
        bool isneg=false;
        if(x<=INT_MIN)
            return 0;
        
        if(x<0){
            isneg=true;
            x=-x;
        }   
        int ans=0;
        while(x>0)
        {
            if(ans>INT_MAX/10)
                return 0;
            ans=ans*10+(x%10);
            x/=10;
        }
        return isneg?-ans:ans;
        
    }
};
```
