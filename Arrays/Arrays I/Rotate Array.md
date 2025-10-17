# Rotate Array

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(1)

```cpp
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
        k=k%nums.size();
        int y=nums.size()-k;
        reverse(nums.begin(), nums.begin()+y);
        reverse(nums.begin()+y, nums.end());
        reverse(nums.begin(), nums.end());
    }
};
```
