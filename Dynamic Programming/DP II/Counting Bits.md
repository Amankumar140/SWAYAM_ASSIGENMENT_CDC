# Counting Bits

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(n)

```cpp
class Solution {
public:
    vector<int> countBits(int n) {
        vector<int> dp(n + 1, 0);
        int offset = 1;
        for (int i = 1; i <= n; i++) {
            if (i == offset * 2)
                offset = i;
            dp[i] = 1 + dp[i - offset];
        }
        return dp;
    }
};
```
