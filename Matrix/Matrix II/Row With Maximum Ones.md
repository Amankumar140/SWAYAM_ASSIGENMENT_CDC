# Row With Maximum Ones

**Programming Lang :** C++

**Time Complexity :** O(n*n)  
**Space Complexitiy :** O(1)

```cpp
class Solution {
public:
    vector<int> rowAndMaximumOnes(vector<vector<int>>& mat) {
        int m = mat.size();
        int n = mat[0].size();

        int maxCount = -1;
        int idx = -1;
        for (int i = 0; i < m; i++) {
            int count = 0;
            for (int j = 0; j < n; j++) {
                if (mat[i][j] == 1) {
                    count++;
                }
            }
            if (count > maxCount) {
                maxCount = count;
                idx = i;
            }
        }
        return { idx, maxCount};
    }
};
```
