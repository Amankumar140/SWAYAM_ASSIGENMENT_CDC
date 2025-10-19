# Missing Number

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(1)

```cpp
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n = nums.size();
        int xorAll = 0;
        for (int i = 0; i <= n; i++)
            xorAll ^= i;
        for (int num : nums)
            xorAll ^= num;
        return xorAll;
    }
};

```
