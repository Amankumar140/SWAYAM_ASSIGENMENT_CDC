# Single Number

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(1)

```cpp
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int a=0;
        for(int val:nums)
        {
            a^=val;
        }
        return a;
        
    }
};

```
