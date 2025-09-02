#   [1021. Remove Outermost Parentheses](https://leetcode.com/problems/remove-outermost-parentheses/)
- have a balance variable 
- learn to use `if else` better
```cpp
string removeOuterParentheses(string s) {
        int balance=0;
        string ans="";
        for(int i=0;i<s.size();i++){
            if(s[i]=='('){
                balance++;
                if(balance>1) ans+=s[i];
  
            }else {
                balance--;
                if(balance>0) ans+=s[i];
            }
        }
        return ans;
    }
```
# [151. Reverse Words in a String](https://leetcode.com/problems/reverse-words-in-a-string/)
- m
```cpp
```

#   [1903. Largest Odd Number in String](https://leetcode.com/problems/largest-odd-number-in-string/)
- logic -> from last, check for odd no, if found , from last add it another string
- reverse that string
```cpp
    string largestOddNumber(string num) {
        string ans;
        int n=num.size();
        int i;
        for(int j=n-1;j>=0;j--){
            if(int(num[j])%2!=0) {
                i=j;
                break;
            }
        }
        for(int j=i;j>=0;j--){
            ans.push_back(num[j]);
        }
        reverse(ans.begin(), ans.end());
        return ans;
  
    }
```
# [14. Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/)
- m
```cpp
```

# 
- m
```cpp
```