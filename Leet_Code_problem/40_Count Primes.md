# 204. Count Primes

Given an integer n, return the number of prime numbers that are strictly less than n.

Example 1:

Input: n = 10
Output: 4
Explanation: There are 4 prime numbers less than 10, they are 2, 3, 5, 7.

Example 2:

Input: n = 0
Output: 0

Example 3:

Input: n = 1
Output: 0

Constraints:

    0 <= n <= 5 * 106

# Java
seive approach
```
class Solution {
    public int countPrimes(int n) {
       if(n<=1)
        return 0;

        boolean [] isprime=new boolean[n];
        for(int i=0;i<n;i++)
            isprime[i]=true;
        isprime[0]=isprime[1]=false;

        int ans=0;

        for(int i=2;i<n;i++){
            if(isprime[i]){
                ans++;

                int j=2*i;
                while(j<n){
                    isprime[j]=false;
                    j=j+i;
                }
            }
        }

    return ans;
    }   
}
```

