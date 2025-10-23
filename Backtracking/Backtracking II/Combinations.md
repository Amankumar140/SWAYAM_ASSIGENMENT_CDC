# Combinations

**Programming Lang :** C++

**Time Complexity :** O(k*C(n,k))  
**Space Complexitiy :** O(k*C(n,k))

```cpp
 class Solution {
public:
    void backtrack(int n, int k, int i, vector<int>& res,
                   vector<vector<int>>& ans) {
        if (res.size() >= k) {
            ans.push_back(res);
            return;
        }
        for (int j = i; j <= n; j++) {
            res.push_back(j);
            backtrack(n, k, j + 1, res, ans);
            res.pop_back();
        }
    }
    vector<vector<int>> combine(int n, int k) {
        vector<int> res;
        vector<vector<int>> ans;
        backtrack(n, k, 1, res, ans);
        return ans;
    }
};
```
