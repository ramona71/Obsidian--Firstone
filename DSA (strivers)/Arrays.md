# Second largest and smallest
- ![[Pasted image 20250119125805.png]]
```cpp
int getSecondLargest(vector<int> &arr) {
        // Code Here
        int largest=arr[0];
        int n=arr.size();
        int Slargest=-1;
        for(int i=1;i<n;i++){
            if(arr[i]>largest){
                Slargest= largest;
                largest= arr[i];
            }
            else if(arr[i]>Slargest&& arr[i]!=largest){
                Slargest= arr[i];
            }
        }
        return Slargest;
    }
```
# Check if array is sorted
```cpp
```
# Remove duplicates from sorted
```cpp
int removeDuplicates(vector<int>& nums) {
        int n= nums.size();
        int i=0;
        for(int j=1;j<n;j++){
            if(nums[i]!=nums[j]){
                nums[i+1]=nums[j];
                i++;
            }
        }
        return i+1;
  }
```
# Right Rotate
```cpp
void rotate(vector<int>& nums, int k) {
        int n=nums.size();
        k=k%n;
        vector<int> temp;
        for(int i=0;i<k;i++){
            temp.push_back(nums[n-k+i]);
        }
        for(int i=n-1;i>=k;i--){
            nums[i]= nums[i-(k)];
        }
        for(int i=0;i<k;i++){
            nums[i]= temp[i];
        }
    }
```
# Move Zeroes to the end
```cpp
void moveZeroes(vector<int>& nums) {
        int n=nums.size();
        int j=-1;
        int i=0;
        for(i=0;i<n;i++){
            if(nums[i]==0){
                j=i;
                break;
            }
        }
        if(j>=0){
            for(i=j+1;i<n;i++){
            if(nums[i]!=0){
                swap(nums[i], nums[j]);
                j++;
            }
        }
        }
    }
```
# [1752. Check if Array Is Sorted and Rotated](https://leetcode.com/problems/check-if-array-is-sorted-and-rotated/)
```cpp
    bool check(vector<int>& nums) {
       int n=nums.size();
       int count=0;
       for(int i=0;i<n;i++){
        if(nums[i]>nums[(i+1)%n] )
            count++;
        if(count>1) return false;
       }
      return true;
    }
```
# [169. Majority Element](https://leetcode.com/problems/majority-element/)
- Brute -> sort it and find the element at n/2 index
- my optimized -> use a hash map, add count of each element , traverse the count of each element, whateve has n/2> count that is the ans
```cpp
 int majorityElement(vector<int>& nums) {
        unordered_map<int,int> mmpp;
        int element=0;
        int n=nums.size();
        for(int x: nums){
            mmpp[x]++;
        }
        for(auto x : mmpp){
            if(x.second>n/2) return x.first;
        }
        return -1;
    }
```
- even more optimised (space complexity O(1))
```cpp
int majorityElement(vector<int>& nums) {
    int candidate = 0, count = 0;
    for (int num : nums) {
        if (count == 0) {
            candidate = num;
        }
        count += (num == candidate) ? 1 : -1;
    }
    return candidate;}
```