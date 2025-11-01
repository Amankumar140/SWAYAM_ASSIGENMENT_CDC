# Coin change

**Programming Lang :** C++

**Time Complexity :** O(n*m)  
**Space Complexitiy :** O(n*m)

```cpp
class Solution {
public:
    int solve(vector<int>& coins, int n, int i) {
        if (n <= 0)
            return 0;

        if (i >= coins.size())
            return -1;
        int x = -1;
        if (coins[i] <= n) {
            x = solve(coins, n - coins[i], i);
        }

        int y = solve(coins, n, i + 1);
        if (x == -1 && y == -1)
            return -1;
        if (y == -1)
            return x + 1;
        if (x == -1)
            return y;
        return min(x + 1, y);
    }
    int coinChange(vector<int>& coins, int amount) {
        return solve(coins, amount, 0);
    }
};

```
