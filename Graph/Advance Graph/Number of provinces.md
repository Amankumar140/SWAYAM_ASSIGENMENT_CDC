# Number of Provinces

**Programming lang :** C++

**Time complexity :** O(v+e)  
**space Complexity:** O(v)


```cpp
class Solution {
public:
    int findCircleNum(vector<vector<int>>& isConnected) {
        int n = isConnected.size();
        vector<bool> visited(n + 1, false);
        int provinces = 0;
        for (int i = 0; i < n; i++) {
            if (!visited[i]) {
                bfs(isConnected, i, visited);
                provinces++;
            }
        }
        return provinces;
    }
    void bfs(vector<vector<int>>& isConnected, int s, vector<bool>& visited) {
        queue<int> q;
        q.push(s);
        visited[s] = true;
        while (!q.empty()) {
            int curr = q.front();
            q.pop();
            for (int i = 0; i < isConnected.size(); i++) {
                if (isConnected[curr][i] == 1 && !visited[i]) {
                    visited[i] = true;
                    q.push(i);
                }
            }
        }
    }
};
```
