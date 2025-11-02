# Target Sum

**Programming Lang :** C++

**Time Complexity :** O(n x psum)  
**Space Complexitiy :** O(psum)

```cpp
    class Solution {
public:
    int findTargetSumWays(vector<int>& nums, int target) {
        int sum = accumulate(nums.begin(), nums.end(), 0);
        if (abs(target) > sum || (sum + target) % 2 != 0)
            return 0;

        int psum = (target + sum) / 2;
        vector<int> dp(psum + 1, 0);
        dp[0] = 1;
        for (int i = 0; i < nums.size(); i++) {
            for (int j = psum; j >= nums[i]; j--) {
                dp[j] += dp[j - nums[i]];
            }
        }
        return dp[psum];
    }
};
```
