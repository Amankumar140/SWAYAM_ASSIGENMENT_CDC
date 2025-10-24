# 0-1 Knapsack Problem

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(n)

```cpp

class Solution {
  public:
     int knapsack(int w, vector<int> &val, vector<int> &wt) {
        // code here
        int n=val.size();
        vector<int> dp(w+1,0);
        for (int i=0;i<n;i++){
            for(int j=w;j>=wt[i];j--){
                dp[j]=max(dp[j],val[i]+dp[j-wt[i]]);
            }
        }
        return dp[w];
    }
};
```
