# House Robber

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(n)

```cpp
class Solution {
public:
    int robbing(vector<int>& nums, int i, int size, vector<int>& dp) {
        if (i >= size)
            return 0;
        if (dp[i] != -1)
            return dp[i];
        int opt1 = nums[i] + robbing(nums, i + 2, size, dp);
        int opt2 = 0 + robbing(nums, i + 1, size, dp);
        dp[i] = max(opt1, opt2);
        return dp[i];
    }
    int rob(vector<int>& nums) {
        vector<int> dp(nums.size(), -1);
        return robbing(nums, 0, nums.size(), dp);
    }
};
```
