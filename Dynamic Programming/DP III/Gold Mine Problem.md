# Gold Mine Problem

**Programming Lang :** C++

**Time Complexity :** O(n x m)  
**Space Complexitiy :** O(n x m)

```cpp
 class Solution {
  public:
    int maxGold(vector<vector<int>>& mat) {
        // code here
        int n= mat.size();
        int m= mat[0].size();
        vector<vector<int>> dp (n, vector<int> (m, 0));
        
        for(int i=0; i<n; i++){
            dp[i][m-1]= mat[i][m-1];
        }
        for(int j=m-2; j>=0; j--){
            for(int i=0; i<n; i++){
                int r= dp[i][j+1];
                int ru= (i>0 )? dp[i-1][j+1] : 0;
                int rd= (i<n-1 )? dp[i+1][j+1] : 0;
                dp[i][j]=  max({r, ru, rd})+ mat[i][j];
            }
        }
        int ans = 0;
        for (int i = 0; i < n; i++) {
            ans = max(ans, dp[i][0]);
        }

        return ans;
    }
};

```
