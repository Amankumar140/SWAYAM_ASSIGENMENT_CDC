# Combination Sum II

**Programming Lang :** C++

**Time Complexity :** O(n^T × T)  
**Space Complexitiy :** O(T × number of valid combinations)

```cpp
 class Solution {
public:
    vector<vector<int>> res;
    vector<int> ans;

    void helper(vector<int>& nums, int target, int idx=0) {
        if (target == 0) {
            res.push_back(ans);
            return;
        }
        for (int i = idx; i < nums.size(); i++) {
            // Skip duplicates
            if (i > idx && nums[i] == nums[i - 1])
                continue;

            if (nums[i] > target)
                break;

            ans.push_back(nums[i]);
            helper(nums, target - nums[i], i + 1); // move to next index
            ans.pop_back();
        }
    }
    vector<vector<int>> combinationSum2(vector<int>& candidates, int target) {
        res.clear();
        ans.clear();
        sort(candidates.begin(), candidates.end());
        helper(candidates, target);
        return res;
    }
};
```
