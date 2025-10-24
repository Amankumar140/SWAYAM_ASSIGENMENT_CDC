# Max Chunks To Make Sorted

**Programming Lang :** C++

**Time Complexity :** O(n)  
**Space Complexitiy :** O(1)

```cpp
class Solution {
public:
    int maxChunksToSorted(vector<int>& arr) {
        int currSum = 0, expectedSum = 0, chunks = 0;
        for (int i = 0; i < arr.size(); i++) {
            currSum += arr[i];
            expectedSum += i;
            if (currSum == expectedSum) {
                chunks++;
            }
        }
        return chunks;
    }
};
```
