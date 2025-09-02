- this is working whether i put '&' or not
```cpp
int ImprovedLinearSearch2(struct Array *arr, int key){
    for(int i=0;i<arr->length;i++){
        if(arr->A[i]==key){
            swap(&arr->A[i],&arr->A[0]);             // this is working even if i put the '&' or not
            return 0
        }
    }
    return -1;
}
```
> [!Answer]
> The standard swap function in C++ works with references, so it directly modifies the values in memory.

- third largest
```cpp
// C++ program for find the largest 
// three elements in an array
#include <bits/stdc++.h>
using namespace std;

// Function to return three largest elements
vector<int> get3largest(vector<int> &arr)
{
    int fst = INT_MIN, sec = INT_MIN, thd = INT_MIN;

    for (int x : arr)
    {
        // If current element is greater than fst
        if (x > fst)
        {
            thd = sec;
            sec = fst;
            fst = x;
        }

        // If x is between fst and sec
        else if (x > sec && x != fst)
        {
            thd = sec;
            sec = x;
        }

        // If x is between sec and thd
        else if (x > thd && x != sec && x != fst)
            thd = x;
    }

    vector<int> res = {};
    if (fst == INT_MIN)
        return res;
    res.push_back(fst);
    if (sec == INT_MIN)
        return res;
    res.push_back(sec);
    if (thd == INT_MIN)
        return res;
    res.push_back(thd);
    return res;
}

// Driver code
int main()
{
    vector<int> arr = {34, 34, 11, 9, 14, 34, 14};
    vector<int> res = get3largest(arr);
    for (int x : res)
        cout << x << " ";
    cout << endl;
    return 0;
}
```
 - leader of array
 - The idea is to scan all the elements from ****right to left**** in an array and keep track of the maximum till now. When the maximum changes its value, add it to the result. Finally reverse the result
 ```cpp
 #include <bits/stdc++.h>
using namespace std;

// Function to find the leaders in an array
vector<int> leaders(vector<int>& arr) {
    vector<int> res; 
    int n = arr.size();

    // Start with the rightmost element
    int maxRight = arr[n - 1]; 

    // Rightmost element is always a leader
    res.push_back(maxRight); 
    
    // Traverse the array from right to left
    for (int i = n - 2; i >= 0; i--) {

        if (arr[i] > maxRight) {
            maxRight = arr[i]; 
            res.push_back(maxRight); 
        }
    }

    // Reverse the result array to maintain
    // original order
    reverse(res.begin(), res.end());
    
    return res; 
}

int main() {
    vector<int> arr = { 16, 17, 4, 3, 5, 2 };
    vector<int> res = leaders(arr);
    for (int x : res) {
        cout << x << " ";
    }
    cout << endl;

    return 0;
}
```
- array sorted or not
```cpp
bool isSorted(const vector<int>& arr)
{
    // For an array to be sorted, every
    // element must be greater than the 
    // previous element
    for (int i = 1; i < arr.size(); i++)
        if (arr[i - 1] > arr[i])
            return false;

    return true;
}
// recursive
bool isSorted(const vector<int>& arr, int n)
{
    // Base case
    if (n == 1 || n == 0)
        return true;

    // Check if current and previous elements are in order
    // and recursively check the rest of the array
    return arr[n - 1] >= arr[n - 2] && isSorted(arr, n - 1);
}
```
- IntroSort. In more details it is implemented using hybrid of QuickSort, HeapSort and InsertionSort.By default, it uses QuickSort but if QuickSort is doing unfair partitioning and taking more than N*logN time, it switches to HeapSort and when the array size becomes really small, it switches to InsertionSort.