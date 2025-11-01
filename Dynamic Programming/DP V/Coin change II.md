# Coin change II

**Programming Lang :** C++

**Time Complexity :** O(n*m)  
**Space Complexitiy :** O(n*m)

```cpp
class Solution {
public:
    int change(int amount,vector<int>& coins ) {
        int n = coins.size();
        vector<vector<int>> dp(n + 1, vector<int>(amount + 1, -1));
        return countWays(coins, n, amount, dp);
    }

    int countWays(vector<int>& coins, int n, int amount, vector<vector<int>>& dp) {
        if (amount == 0) return 1;       
        if (n == 0) return 0;           

        if (dp[n][amount] != -1) return dp[n][amount];

        if (coins[n - 1] <= amount) {
             
            dp[n][amount] = countWays(coins, n, amount - coins[n - 1], dp) +
                            countWays(coins, n - 1, amount, dp);
        } else {
            
            dp[n][amount] = countWays(coins, n - 1, amount, dp);
        }

        return dp[n][amount];
    }
};


```
