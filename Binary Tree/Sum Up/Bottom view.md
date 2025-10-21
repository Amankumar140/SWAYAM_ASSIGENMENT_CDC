# Bottom View

**Programming Lang :** C++

**Time Complexity :** O(n log n)  
**Space Complexitiy :** O(n)
 
```cpp
 
class Solution {
  public:
    vector<int> bottomView(Node *root) {
        // code here
        queue<pair<Node* ,int>>q;
        map<int, int> m; // hd, data
        q.push({root,0});
        
        while(!q.empty()){
            auto [node, hd]= q.front();
            q.pop();
            
            m[hd]=node->data; // override everytime for bottom 
            if(node->left){
                q.push({node->left, hd-1});
            }
            if(node->right){
                q.push({node->right, hd+1});
            }
        }
        vector<int> ans;
        for(auto &p : m){
            ans.push_back(p.second);
        }
        return ans;
    }
};
```
