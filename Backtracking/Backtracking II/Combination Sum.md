# Combination Sum

**Programming Lang :** C++

**Time Complexity :** O(n^T × T)  
**Space Complexitiy :** O(T × number of valid combinations)

```cpp
class Solution {
public:
    vector<vector<int>> res;
    vector<int> ans;
    void helper(vector<int> nums, int target, int idx = 0, int currsum = 0) {

        if (currsum == target) {
            res.push_back(ans);
            return;
        }

        if (idx == nums.size() || currsum > target) {
            return;
        }

        ans.push_back(nums[idx]);
        helper(nums, target, idx, currsum + nums[idx]);
        ans.pop_back();
        helper(nums, target, idx + 1, currsum);
    }
    vector<vector<int>> combinationSum(vector<int>& candidates, int target) {
        res.clear();
        ans.clear();
        helper(candidates, target);
        return res;
    }
};
```
