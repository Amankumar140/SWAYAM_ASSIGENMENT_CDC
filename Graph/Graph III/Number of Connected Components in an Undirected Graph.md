# Number of Connected Components in an Undirected Graph

**Programming lang :** C++

**Time complexity :** O(n+m)  
**space Complexity:** O(n+m)


```cpp
class Solution {
public:
    int countComponents(int n, vector<vector<int>>& edges) {
        vector<bool>visited(n, false);

        vector<vector<int>> adj(n);
        for (auto &e : edges) {
            adj[e[0]].push_back(e[1]);
            adj[e[1]].push_back(e[0]);
        }

        int compo=0;
        for(int i=0; i<n; i++){
            if(!visited[i]){
                bfs(adj,n,i,visited);
                compo++;
            }
        }
        return compo;
    }
    void bfs(vector<vector<int>>&adj, int n, int s, vector<bool>&visited){
        queue<int>q;
        visited[s]=true;
        q.push(s);
        while(!q.empty()){
            int curr=q.front();
            q.pop();
            for(int x : adj[curr]){
                if(!visited[x]){
                    visited[x]=true;
                    q.push(x);
                }
            }
        }
    }
};

```
