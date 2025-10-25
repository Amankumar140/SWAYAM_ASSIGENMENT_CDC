# Prims`s algo

**Programming lang :** C++

**Time complexity :** O(e log v)  
**space Complexity:** O(v+e)


```cpp
class Solution {
  public:
    int spanningTree(int V, vector<vector<int>>& edges) {
        // code here
            vector<vector<pair<int,int>>> adj(V);
for(auto &e : edges){
    int u = e[0];
    int v = e[1];
    int wt = e[2];
    adj[u].push_back({v, wt});
    adj[v].push_back({u, wt}); // because it's undirected
}

        int sum=0;
        priority_queue<pair<int,int>,vector<pair<int,int>>,greater<pair<int,int>>>pq;
        vector<int>visit(V,0);
        //{wt,node}
        pq.push({0,0});
        
        while(!pq.empty()){
            auto t=pq.top();
            pq.pop();
            int wt=t.first;
            int node=t.second;
            if(visit[node]) continue;
            visit[node]=1;
            sum+=wt;
            for(auto it:adj[node]){
                if(!visit[it.first]){
                pq.push({it.second,it.first});
                }
            }
        }
        
        return sum;
    }
};
  
```
