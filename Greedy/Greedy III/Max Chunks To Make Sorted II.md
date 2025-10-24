# Max Chunks To Make Sorted II

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(n)

```cpp
class Solution {
public:
    int maxChunksToSorted(vector<int>& arr) {
         int n = arr.size();
        vector<int> leftMax(n), rightMin(n);

        // Compute prefix maximums
        leftMax[0] = arr[0];
        for (int i = 1; i < n; ++i)
            leftMax[i] = max(leftMax[i - 1], arr[i]);

        // Compute suffix minimums
        rightMin[n - 1] = arr[n - 1];
        for (int i = n - 2; i >= 0; --i)
            rightMin[i] = min(rightMin[i + 1], arr[i]);

        // Count valid cuts
        int chunks = 0;
        for (int i = 0; i < n - 1; ++i) {
            if (leftMax[i] <= rightMin[i + 1])
                chunks++;
        }

        return chunks + 1;
    }
};
```
