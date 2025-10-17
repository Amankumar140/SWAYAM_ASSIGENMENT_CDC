# Maximum Subarray

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(1)

```cpp
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int sum=0;
        int maxSum=INT_MIN;
        for(int n: nums){
            sum+=n;
            maxSum=max(maxSum,sum);
            if(sum<0) sum=0;
        }
        return maxSum;
    }
};
```
