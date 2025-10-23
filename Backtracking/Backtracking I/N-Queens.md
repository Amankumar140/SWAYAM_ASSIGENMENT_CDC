# N-Queens

**Programming Lang :** C++

**Time Complexity :** O(n * n!)  
**Space Complexitiy :** O(n*n)

```cpp
class Solution {
public:
    vector<vector<string>> ans;

    bool valid(vector<string>& board, int n, int row, int j) {
        for (int i = 0; i < n; i++) {
            if (board[row][i] == 'Q')
                return false;
            if (board[i][j] == 'Q')
                return false;
        }

        for (int i = row, k = j; i >= 0 && k >= 0; i--, k--) {
            if (board[i][k] == 'Q')
                return false;
        }
        for (int i = row, k = j; i >= 0 && k < n; i--, k++) {
            if (board[i][k] == 'Q')
                return false;
        }
        return true;
    }

    void nqueens(vector<string>& board, int n, int row = 0) {
        if (row == n) {
            ans.push_back(board);
            return;
        }
        for (int i = 0; i < n; i++) {
            if (valid(board, n, row, i)) {
                board[row][i] = 'Q';
                nqueens(board, n, row + 1);
                board[row][i] = '.';
            }
        }
    }

    vector<vector<string>> solveNQueens(int n) {
        vector<string> board(n, string(n, '.'));
        nqueens(board,n);
        return ans;
    }
};
```
