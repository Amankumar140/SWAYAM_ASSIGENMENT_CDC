# Remove Duplicates from Sorted Array

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(1)

```cpp
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        int i=0;
        for(int j=1; j<nums.size(); j++){
            if(nums[i]==nums[j]) continue;
            else{
                i++;
                swap(nums[i],nums[j]);
            }
        }
         
        return i+1;
    }
};
```
