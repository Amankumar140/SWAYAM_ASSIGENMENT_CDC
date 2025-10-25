# Directed Graph Cycle

**Programming lang :** C++

**Time complexity :** O(n+m)  
**space Complexity:** O(n+m)


```cpp
class Solution {
  public:
  
    vector<vector<int>>adj;
    void adjList(int V, vector<vector<int>>& edges){
        adj.assign(V,vector<int>());
        for(auto &e : edges){
            int u=e[0],v=e[1];
            adj[u].push_back(v);
        }
    }
    
    bool dfsRec(  int s, vector<bool> &visited, vector<bool> &recst){
        visited[s]=true;
        recst[s]=true;
        for(int u: adj[s]){
            if(!visited[u] && dfsRec(u,visited,recst)) return true;
            else if(recst[u]) return true;
            
        }
        
        recst[s]=false;
        return false;
    }
    
    bool dfs(int V){
        vector<bool>visited(V,false);
        vector<bool>recst(V,false);
        for(int i=0; i<V; i++){
            if(!visited[i]){
                if(dfsRec(i,visited,recst)) return true;
            }
        }
        return false;
    }
    
    bool isCyclic(int V, vector<vector<int>> &edges) {
         adjList(V,edges);
        return dfs(V);
    }
};
```
