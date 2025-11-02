# Path with Maximum Gold

**Programming Lang :** C++

**Time Complexity :** O(n x m)  
**Space Complexitiy :** O(n x m)

```cpp
 class Solution {
public:
    int solve(vector<vector<int>>& grid, int i, int j,
              vector<vector<bool>>& vis) {
        int m = grid.size();
        int n = grid[0].size();
        if (i >= m || j >= n || i < 0 || j < 0 || grid[i][j] == 0 || vis[i][j])
            return 0;

        vis[i][j] = true;
        int gold = grid[i][j];
        int up = solve(grid, i - 1, j, vis);
        int down = solve(grid, i + 1, j, vis);
        int right = solve(grid, i, j + 1, vis);
        int left = solve(grid, i, j - 1, vis);
        vis[i][j] = false;

        return gold + max({up, down, right, left});
    }
    int getMaximumGold(vector<vector<int>>& grid) {
        int m = grid.size();
        int n = grid[0].size();
        int ans = 0;

        vector<vector<bool>> vis(m, vector<bool>(n, false));
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (grid[i][j] != 0) {
                    ans = max(ans, solve(grid, i, j, vis));
                }
            }
        }
        return ans;
    }
};
```
