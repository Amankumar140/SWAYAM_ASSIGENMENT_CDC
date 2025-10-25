# DFS Traversal

**Programming lang :** C++

**Time complexity :** O(v+e)  
**space Complexity:** O(v)


```cpp
class Solution {
  public:
    vector<int>ans;
    void dfsRec(vector<vector<int>>& adj , int s, vector<bool> &visited){
        visited[s]=true;
        ans.push_back(s);
        for(int u : adj[s]){
            if(!visited[u]){
                dfsRec(adj,u,visited);
            }
        }
    }
    
     
    vector<int> dfs(vector<vector<int>>& adj) {
         vector<bool>visited(adj.size()+1,false);
         dfsRec(adj,0,visited);
         return ans;
        
    }
};
```
