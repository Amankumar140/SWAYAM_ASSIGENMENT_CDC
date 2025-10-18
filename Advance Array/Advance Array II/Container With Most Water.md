# Container With Most Water  

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(1)

```cpp
class Solution {
public:
    int maxArea(vector<int>& height) {
        int s = 0, e = height.size() - 1;
        int maxAmt = 0;
        while (s < e) {
            int width = e - s;
            int ht = min(height[s], height[e]);
            maxAmt = max(maxAmt, ht * width);
            height[s] < height[e] ? s++ : e--;
        }
        return maxAmt;
    }
};
```
