#  Set Matrix Zeroes

**Programming Lang :** C++

**Time Complexity :** O(n*m)  
**Space Complexitiy :** O(n+m)

```cpp
 class Solution {
public:
    void setZeroes(vector<vector<int>>& matrix) {
        int m = matrix.size();
        int n = matrix[0].size();
        unordered_set<int> rows;
        unordered_set<int> cols;

        // Step 1: Record rows and columns that contain 0
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (matrix[i][j] == 0) {
                    rows.insert(i);
                    cols.insert(j);
                }
            }
        }

        // Step 2: Set zeros based on recorded rows and columns
        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                if (rows.count(i) || cols.count(j)) {
                    matrix[i][j] = 0;
                }
            }
        }
    }
};


```
