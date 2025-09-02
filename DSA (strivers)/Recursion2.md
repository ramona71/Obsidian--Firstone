# Takeaways
- always , always include if(n<=0) return;
	- always keep a base condition if the no decrements to 0
# print Gfg n times
```cpp
class Solution {
  public:
    void printGfg(int N) {
        if(N<=0) return;
        cout<<"GFG";
        if(N>1) cout<<" ";
        printGfg(N-1);
    }
};
```
# print 1 to n
- BACKTRACKING!!!!!!
```cpp
void printNos(int n) {
        if(n<=0) return ;
        printNos(n-1);
        if(n>1) cout<<" ";
        cout<<n;
    }
```
# print n to 1 ( the easiest tf)
```cpp
void printNos(int N) {
        if(N<=0) return;
        cout<<N;
        if(N>1) cout<<" ";
        printNos(N-1);
        // code here
    }
```
# Print sum of n^3
- logic is `3+f(2)` 
```cpp
  int sumOfSeries(int n) {
        if(n<1) return 0;
        return (n*n*n)+sumOfSeries(n-1);
```
# Reverse an array (iterative)
```cpp
void reverseArray(vector<int> &arr) {
        // code here
        int n=arr.size();
        int i=0;
        while(i<n/2){
            swap(arr[i], arr[n-i-1]);
            i++;
        }
    }
```
# palindrome reverse
```cpp
bool isPalindrome(string s) {
        int n=s.size();
        int left=0, right= n-1;
        while(left<right){
            while(left<right && !isalnum(s[left])) left++;
            while(left<right && !isalnum(s[right])) right--;
            if(tolower(s[left])!=tolower( s[right])) return false;
            left++;
            right--;  
        }
        return true;
    }
```
