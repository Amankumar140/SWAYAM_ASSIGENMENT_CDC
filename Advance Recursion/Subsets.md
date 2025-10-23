# Subsets

**Programming Lang :** C++

**Time Complexity :** O(n * 2^n)  
**Space Complexitiy :** O(n)

```cpp
  class Solution {
public:
    void help(vector<int>& nums, int i, vector<int>& res,
              vector<vector<int>>& ans) {
        if (i >= nums.size()) {
            ans.push_back(res);
            return;
        }
        // include
        res.push_back(nums[i]);
        help(nums, i + 1, res, ans);
        res.pop_back();
        help(nums, i + 1, res, ans);
    }
    vector<vector<int>> subsets(vector<int>& nums) {
        vector<int> res;
        vector<vector<int>> ans;
        help(nums, 0, res, ans);
        return ans;
    }
};
```
