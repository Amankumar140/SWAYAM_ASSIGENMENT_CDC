# BFS Traversal

**Programming lang :** C++

**Time complexity :** O(v+e)  
**space Complexity:** O(v)


```cpp
class Solution {
  public:
  
    // Function to return Breadth First Traversal of given graph.
    vector<int> bfs(vector<vector<int>> &adj) {
         
        vector<bool> visited(adj.size()+1,false);
        vector<int> ans;
        queue<int>q;
        //int s=adj[0][0];
        q.push(0);
        visited[0]=true;
        while(!q.empty()){
            int u=q.front();
            q.pop();
            ans.push_back(u);
            for(int x: adj[u]){
                if(!visited[x]){
                    visited[x]=true;
                    q.push(x);
                }
            }
        }
        return ans;
    }
};
```
