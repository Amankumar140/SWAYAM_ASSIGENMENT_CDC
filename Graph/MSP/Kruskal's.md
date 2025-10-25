# Prims`s algo

**Programming lang :** C++

**Time complexity :** O(e log v)  
**space Complexity:** O(v+e)


```cpp

class DisjointSet
{
    vector<int> rank, parent, size;

public:
    DisjointSet(int n)
    {
        rank.resize(n + 1, 0);
        size.resize(n + 1, 1);
        parent.resize(n + 1);
        for (int i = 0; i <= n; i++)
        {
            parent[i] = i;
        }
    }

    int findParent(int node)
    {
        if (node == parent[node])
        {
            return node;
        }
        return parent[node] = findParent(parent[node]);
    }

    void unionByRank(int u, int v)
    {
        int ulp_u = findParent(u);
        int ulp_v = findParent(v);

        if (ulp_v == ulp_u)
            return;
        if (rank[ulp_u] < rank[ulp_v])
        {
            parent[ulp_u] = ulp_v;
        }
        else if (rank[ulp_v] < rank[ulp_u])
        {
            parent[ulp_v] = ulp_u;
        }
        else
        {
            parent[ulp_v] = ulp_u;
            rank[ulp_u]++;
        }
    }

    void unionBySize(int u, int v)
    {
        int ulp_u = findParent(u);
        int ulp_v = findParent(v);

        if (ulp_v == ulp_u)
            return;
        if (size[ulp_u] < size[ulp_v])
        {
            parent[ulp_u] = ulp_v;
            size[ulp_v] += size[ulp_u];
        }
        else
        {
            parent[ulp_v] = ulp_u;
            size[ulp_u] += size[ulp_v];
        }
    }
};




class Solution {
  public:
    int spanningTree(int V, vector<vector<int>>& edges) {
        vector<pair<int,pair<int,int>>>adj;
         
            for(auto it : edges){
                adj.push_back({it[2],{it[0],it[1]}});
            }
        
        
        sort(adj.begin(),adj.end());
        int mstwt=0;
        
        DisjointSet ds(V);
        for(auto it: adj ){
            int u=it.second.first;
            int v=it.second.second;
            int wt=it.first;
            if(ds.findParent(u)!=ds.findParent(v)){
                mstwt+=wt;
                ds.unionBySize(u,v);
            }
        }
        return mstwt;
        
    }
};
  
```
