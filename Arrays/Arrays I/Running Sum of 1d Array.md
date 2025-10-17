# Running Sum of 1d Array

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(n)

```cpp
  class Solution {
public:
    vector<int> runningSum(vector<int>& nums) {
        int n = nums.size();
        vector<int> ans(n);
        ans[0] = nums[0];
        for (int i = 1; i < n; i++) {
            ans[i] = ans[i - 1] + nums[i];
        }
        return ans;
    }
};
```

## Optimize (Space) 

**Time Complexity :** O(n)  
**Space Complexitiy :** O(1)

```cpp
 class Solution {
public:
    vector<int> runningSum(vector<int>& nums) {
        int n = nums.size();

        for (int i = 1; i < n; i++) {
            nums[i] = nums[i - 1] + nums[i];
        }
        return nums;
    }
};
```
