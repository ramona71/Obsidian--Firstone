```
class Solution {
public:
    vector<int> findDisappearedNumbers(vector<int>& nums) {
        for (int num : nums) {
            int index = abs(num) - 1; // Get the index (convert value to 0-based)
            nums[index] = -abs(nums[index]); // Mark it as visited by making it negative
        }
        
        vector<int> ans;
        for (int i = 0; i < nums.size(); i++) 
            if (nums[i] > 0) ans.push_back(i + 1); // Collect unmarked (missing) numbers
        
        return ans;
    }
};


```
- 
```
─$ sudo samdump2 SYSTEM SAM
[sudo] password for alekhya:
*disabled* Administrator:500:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
*disabled* Guest:501:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
alekhya:1001:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
```