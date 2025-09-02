# [70. Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)
- memory exceeded
```cpp
class Solution {
public:
    int stairs(vector<int> dp, int n){
        if (n<=2){
            return n;
        }
        if(dp[n]!=-1) return dp[n];
        return dp[n]= stairs(dp, n-1)+ stairs(dp, n-2);
    }
  
    int climbStairs(int n) {
        vector<int> dp(n+1,-1);
        dp[0]=0;
        dp[1]=1;
        return stairs(dp, n);
    }    
};
```
- accepted -> 100
```cpp
class Solution {
public:
    int climbStairs(int n) {
        int prev2=1,prev1=2;
        if(n<=2) return n;
        int output=0;
        for(int i=3;i<=n;i++){
            output=prev1+prev2;
            prev2=prev1;
            prev1=output;
        }
        return output;
    }    
};
```