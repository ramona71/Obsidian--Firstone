- ![[Pasted image 20241101144146.png]]
- ![[Pasted image 20241101144332.png]]
- ![[Pasted image 20241101144425.png]]
- ![[Pasted image 20241101144511.png]]
-  ![[Pasted image 20241101144553.png]]
- ![[Pasted image 20241101144727.png]]
- ![[Pasted image 20241101144803.png]]
# Contains Duplicate (217)
- my optimized -> put them all in set and check the size
```cpp
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        unordered_set<int> sst;
        for(auto it:nums){
            sst.insert(it);
        }
        if(nums.size() == sst.size()) return false ;
        else return true;
    }
};
```
- 1. brute force -> two loops
- 2. sort and search if element is equal to previous element
- 3. set / map -> 
	1. see if the size of them is same as arrays
	2. during insertion itselt
- even optimized
```cpp
bool containsDuplicate(vector<int>& nums) {
        unordered_set<int> sst;
        for(int x:nums){
	        if(sst.count(x)>0)  return true;
	        sst.insert(x);
	    }
	    return false;
}
// or
       unordered_map<int, int> mmp;
        for (int x : mmp) {
            if (mmp[x] >= 1)
                return true;
            mmp[x]++;
        }
        return false;
    }
```
# Missing no (268)
- my optimized -> find sum of numbers and subtract the array sum
```cpp
    int missingNumber(vector<int>& nums) {
        int n=nums.size();
        int sum=0;
        for(int num: nums){
            sum+=num;
        }
        return (n*(n+1))/2 -sum;
    }
```
1. Brute -> Sort and loop       -> O(n)
2. Optimized -> Sum and subtract (mine)     -> O(n)
3. Hash table ->  O(n)  -> takes extra space
```cpp
   int missingNumber(vector<int>& nums) {
        int n = nums.size();
        vector<int>v(n+1,-1);
        for(int i =0;i<nums.size();i++){
            v[nums[i]] = nums[i];
        }
        for(int i =0;i<v.size();i++){
            if(v[i]==-1)return i;
        }
        return 0;
    }
```
4. XOR -> O(n)
```cpp
    int missingNumber(vector<int>& nums) {
        int n = nums.size();
        int ans =0;
        for(int i =1;i<=n;i++){
            ans = ans ^ i;
        }
        for(int i =0;i<nums.size();i++){
            ans= ans^nums[i];
        }
        return ans;
    }
```
# [448. Find All Numbers Disappeared in an Array](https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/)
- my optimized -> keep them in hash and keep them in another vector to return -> O(n)
```cpp
    vector<int> findDisappearedNumbers(vector<int>& nums) {
        int n=nums.size();
        vector <int> hashh (n+1,-1);
        vector<int> returnHash;
        for(int x:nums) hashh[x]++;
        for(int i=1;i<n+1;i++) {
            if(hashh[i]==-1)
                returnHash.push_back(i);
        }
        return returnHash;
    }
```
5. Brute -> if not present, push them into result array  -> O(n^2)
```cpp
class Solution {
public:
    vector<int> findDisappearedNumbers(vector<int>& nums) {
        vector<int> ans;
        for(int i = 1; i <= size(nums); i++)                  // start from 1, cuz we don't search 0
            if(find(begin(nums), end(nums), i) == end(nums))  // linear search in nums for each i
                ans.push_back(i);
        return ans;
    }
};
```
6. even more optimized->  hash set (same as mine) but looks cool code (can use bool array instead)
```cpp
    vector<int> findDisappearedNumbers(vector<int>& nums) {
        unordered_set<int> s(begin(nums), end(nums));   // insert every nums[i] in hashset
        vector<int> ans(size(nums) - size(s));
        for(int i = 1, j = 0; i <= size(nums); i++)  
            if(!s.count(i)) ans[j++] = i;               // add all elements not found in hashset to ans
        return ans;
    }
```
- Ultra optimized version (space is optimized too)
```cpp
public:
    vector<int> findDisappearedNumbers(vector<int>& nums) {
        vector<int> ans;
        for(auto c : nums)
            nums[abs(c)-1] = -abs(nums[abs(c)-1]);   // mark c is present by negating nums[c-1]
        for(int i = 0; i < size(nums); i++) 
            if(nums[i] > 0) ans.push_back(i+1);      // nums[i] > 0 means i+1 isnt present in nums
        return ans;
    }
};
```

> [!NOTE] Duplicates -> set 
# Two sum
- my optimized -> didn't get it
7. Brute -> two loops
8. optimized-> hash map , find the compliment, if it's present in the array, return that and the current element index
```cpp
 vector<int> twoSum(vector<int>& nums, int target) {
        int n=nums.size();
        unordered_map <int, int> mmp;
        for(int i=0;i<n;i++){
            int compliment= target-nums[i];
            if(mmp.find(compliment)!=mmp.end()){
                return {mmp[compliment],i};
            }
            mmp[nums[i]]=i;
        }
        return {};
    }
```
# Numbers Are Smaller Than the Current no (1365)
- my optimized
```cpp
```
9. Brute -> 
10. even more optimized-> 
```cpp
```
# [ Minimum Time Visiting All Points](https://leetcode.com/problems/minimum-time-visiting-all-points/) (1266)

> [!NOTE] Always understand where the starting point is
> great question to ask the interviewer

- my optimized
```cpp
```
11. Brute -> 
12. even more optimized-> 
```cpp
```
# 
- my optimized
```cpp
```
13. Brute -> 
14. even more optimized-> 
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```
# 
- my optimized
```cpp
```
- even more optimized
```cpp
```