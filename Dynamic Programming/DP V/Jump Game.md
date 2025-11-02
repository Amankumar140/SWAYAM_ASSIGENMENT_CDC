# Jump Game

**Programming Lang :** C++

**Time Complexity :** O(n x n)  
**Space Complexitiy :** O(n)

```cpp
  class Solution {
public:
    bool solve(vector<int>& nums, int i, vector<int>& dp) {
        if (i >= nums.size() - 1)
            return true; // reached end
        if (nums[i] == 0)
            return false; // stuck
        if (dp[i] != -1)
            return dp[i];
        for (int j = 1; j <= nums[i]; j++) {
            if (solve(nums, i + j, dp))
                return dp[i] = true; // found path
        }
        return dp[i] = false; // no valid jump
    }

    bool canJump(vector<int>& nums) {
        vector<int> dp(nums.size(), -1);
        return solve(nums, 0, dp);
    }
};



```
