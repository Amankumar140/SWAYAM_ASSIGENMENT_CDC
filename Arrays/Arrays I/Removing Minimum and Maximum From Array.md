# Removing Minimum and Maximum From Array
**Programming Lang :** C++

**TC =** O(n)  
**SC =** O(1) 

```cpp
  class Solution {
  public:
    int minimumDeletions(vector<int>& nums) {
        int n = nums.size();

        // Find min and max values and their indices
        int mn = INT_MAX, mx = INT_MIN;
        int minIdx = -1, maxIdx = -1;
        for (int i = 0; i < n; i++) {
            if (nums[i] < mn) {
                mn = nums[i];
                minIdx = i;
            }
            if (nums[i] > mx) {
                mx = nums[i];
                maxIdx = i;
            }
        }

        // Calculate all possible deletion strategies
        int left = max(minIdx, maxIdx) + 1;  // remove both from left
        int right = n - min(minIdx, maxIdx); // remove both from right
        int leftRight =
            (minIdx + 1) + (n - maxIdx); // min from left, max from right
        int rightLeft =
            (maxIdx + 1) + (n - minIdx); // max from left, min from right

        // Return minimum of all strategies
        return min({left, right, leftRight, rightLeft});
    }
};

```
