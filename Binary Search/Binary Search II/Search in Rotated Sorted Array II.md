# Search in Rotated Sorted Array    

**Programming Lang :** C++

**Time Complexity :** O(log n)  
**Space Complexitiy :** O(1)

```cpp
class Solution {
public:
    bool search(vector<int>& nums, int target) {
        int low = 0;
        int high = nums.size() - 1;

        while (low <= high) {
            int mid = low + (high - low) / 2;

            if (nums[mid] == target)
                return true;

           
            if (nums[low] == nums[mid] && nums[mid] == nums[high]) {
                low++;
                high--;
                continue;   
            }

            if (nums[low] <= nums[mid]) { // Left half sorted
                if (nums[low] <= target && target < nums[mid])
                    high = mid - 1;
                else
                    low = mid + 1;
            } else { // Right half sorted
                if (nums[mid] < target && target <= nums[high])
                    low = mid + 1;
                else
                    high = mid - 1;    
            }
        }
        return false;
    }
};


```
