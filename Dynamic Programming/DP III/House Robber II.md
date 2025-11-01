# House Robber II

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(n)

```cpp
class Solution {
public:
    int robbing(vector<int>& nums, int n, vector<int>& dp) {
        if (n == 0)
            return nums[0];
        if (n < 0)
            return 0;
        if (dp[n] != -1)
            return dp[n];

        int pick = nums[n] + robbing(nums, n - 2, dp);
        int notPick = robbing(nums, n - 1, dp);
        return dp[n] = max(pick, notPick);
    }

    int solve(vector<int>& nums) {
        int n = nums.size();
        vector<int> dp(n, -1);
        return robbing(nums, n - 1, dp);
    }

    int rob(vector<int>& nums) {
        int n = nums.size();
        if (n == 1)
            return nums[0];
        
        // Case 1: Rob houses [0 .. n-2]
        vector<int> arr1(nums.begin(), nums.end() - 1);
        int case1 = solve(arr1);

        // Case 2: Rob houses [1 .. n-1]
        vector<int> arr2(nums.begin() + 1, nums.end());
        int case2 = solve(arr2);

        return max(case1, case2);
    }
};

```
