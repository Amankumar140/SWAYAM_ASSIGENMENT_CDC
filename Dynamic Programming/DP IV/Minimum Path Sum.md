# Minimum Path Sum

**Programming Lang :** C++

**Time Complexity :** O(n*m)  
**Space Complexitiy :** O(n*m)

```cpp
class Solution {
public:
    int minPathSum(vector<vector<int>>& grid) {
        int m = grid.size();
        int n = grid[0].size();

        vector<vector<int>> dp(m, vector<int>(n, 0));
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (i == 0 && j == 0)
                    dp[i][j] = grid[i][j];
                else {
                    int left = INT_MAX, up = INT_MAX;
                    if (j > 0)
                        left = dp[i][j - 1];
                    if (i > 0)
                        up = dp[i - 1][j];
                    dp[i][j] = grid[i][j] + min(left , up);
                }
            }
        }
        return dp[m - 1][n - 1];
    }
};

```
