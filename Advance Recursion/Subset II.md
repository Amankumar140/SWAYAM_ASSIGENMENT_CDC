# Subset II

**Programming Lang :** C++

**Time Complexity :** O(n * 2^n)  
**Space Complexitiy :** O(n)

```cpp
 class Solution {
  public:
  
    void help(vector<int> & arr, int i, vector<int>& res, vector<vector<int>>& ans ){
         
            ans.push_back(res);
             
        
        for(int j=i; j<arr.size(); j++){
            if(j>i && arr[j]==arr[j-1]) continue;
            
            res.push_back(arr[j]);
            help(arr, j+1, res, ans);
            res.pop_back();
        }
    }
    vector<vector<int>> findSubsets(vector<int>& arr) {
        // code here
        sort(arr.begin(), arr.end());
        vector<int> res;
        vector<vector<int>> ans;
        
        help(arr, 0, res, ans);
        return ans;
        
    }
};
```
