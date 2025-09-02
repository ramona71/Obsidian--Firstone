# Extracting digits
- modulo operator
- divide it by 10 and modulo for next digit and so on 
# Count digits that evenly divide
```cpp
int evenlyDivides(int n) {
        // code here
        int count {0};
        int m=n;
        while(m>0){
            int lastdigit= m%10;
            if(lastdigit!=0 && n%lastdigit==0) count ++;
            m=m/10;
        }
        return count;
    }
```
- Another way
```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n=63254;
    int count= (int)(log10(n)+1);           // main 
    cout<<count;
    return 0;
}
```
	TC : O(log10 N)
# Palindrome
- if reverse no == original number
```cpp
class Solution {
public:
    bool isPalindrome(int x) {
        long long revNum{0};
        if (x >=0) {
            int m = x;
            while (m > 0) {
                int lastDigit = m % 10;
                m = m / 10;
                revNum = (revNum * 10) + lastDigit;
            }
  
        } else
            return false;
        if (x == revNum || x==0 )
            return true;
        return false;
    }
    };
```
![[Pasted image 20250109233134.png]]
# Reverse
```cpp
class Solution {
public:
    int reverse(int x) {
        int rev{0};
        int lastdigit{0};
        while(x!=0){
            if((rev<INT_MIN/10)|| rev>INT_MAX/10) return 0;
            lastdigit=x%10;
            x=x/10;
            rev=rev*10+lastdigit;  
        }
        return rev;
    }
};
```
# Print sum of all divisors
```cpp
class Solution {
  public:
    int sumOfDivisors(int n) {
        // Write Your Code here
        int total_sum{0};
        int sum{0};
        int m=n;
        while(m>0){
            for(int i=1;i<=m;i++){
                if(m%i==0){
                    sum+=i;
                }
            }
            total_sum+=sum;
            m--;
            sum=0;
        }
        return total_sum;
        
    }
};
```
# count prime (min jumps)
- my answer( greedy approach apparently)
```cpp
 int minJumps(vector<int>& arr) {
        // code here
        int n=arr.size();
        int i=0;
        int count=0;
        while(arr[i]){
            i=i+arr[i];
            count++;
            if(i>=n-1) return count;
        }
        return -1;
        
    }
```
