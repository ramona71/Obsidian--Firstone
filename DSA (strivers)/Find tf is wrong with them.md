- 1 . GCD and LCM
```cpp
vector<int> lcmAndGcd(int a, int b) {
        int lcm{0};
        int gcd{0};
        vector<int> vec{0,0};

        while(a>0&& b>0){
            if(a>b) a=a%b;
            else  b=b%b;
        }
        if(a==0) gcd=b;
        else gcd=a;
        
        lcm= (a*b) / gcd;
        vec[0]= lcm;
        vec[1]= gcd;
        return vec;
    }
```
- a, b are changed, and you use the same shit at the end, obviously it's gonna show error dumbass
- 2. reversing an array
```cpp
int n=arr.size();
        int i=0;
        while(i<=n/2){
            swap(arr[i], arr[n-i-1]);
            i++;
        }
```
- hoe ass i<=n/2 means the swap gonna occur again
# palindrom
```cpp
bool isPalindrome(string s) {
        int n=s.size();
        int left=0, right= n-1;
        while(left<right){
            while(left<right && !isalnum(s[left])) left++;
            while(left<right && !isalnum(s[right])) right--;
            if(tolower(s[left])!=toupper( s[right])) return false;
            left++;
            right--;  
        }
        return true;
    }
```
- hoe ass you'll get false always if you compare lowercase letter to uppercase letter
# hash 