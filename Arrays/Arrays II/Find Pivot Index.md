# Find Pivot Index

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(1)

```cpp
class Solution {
public:
    int pivotIndex(vector<int>& nums) {
        int leftSum = 0, rightSum = 0;
        int sum = accumulate(nums.begin(), nums.end(), 0);

        for (int i = 0; i < nums.size(); i++) {

            rightSum = sum - leftSum - nums[i];
            if (leftSum == rightSum)
                return i;
            leftSum += nums[i];
        }
        return -1;
    }
};
```
